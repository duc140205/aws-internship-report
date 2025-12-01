---
title: "Worklog Tuần 12"
date: "2025-09-09"
weight: 2
chapter: false
pre: " <b> 1.12. </b> "
---

### Mục tiêu tuần 12:

* Nắm vững quy trình deploy hạ tầng AWS bằng CDK và hiểu rõ mối quan hệ giữa các stack (VPC, RDS, Lambda, S3, API Gateway).

* Hoàn thiện logic backend cho admin, bao gồm xử lý dữ liệu, thống kê và cơ chế archive RDS → S3.

* Tối ưu cấu trúc hệ thống, refactor code backend và dashboard theo hướng tách biệt nghiệp vụ – dễ maintain – dễ mở rộng.

* Tìm hiểu và triển khai các biện pháp nâng cao hiệu quả xử lý dữ liệu (checksum, giới hạn data load, tối ưu cơ chế đồng bộ).

* Thành thạo việc quản lý tài nguyên AWS thông qua CLI, Console và đảm bảo deploy nhiều lần mà không gây conflict.
### Các công việc cần triển khai trong tuần này:
| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | --------- | ------------ | --------------- | --------------- |
| 2 | - Refactor lại quá trình deploy stack và comment các phần analytics không còn cần thiết.<br> - Điều chỉnh app.py để luôn deploy VPC, RDS và DB Init Stack; bật DashboardStack với dependency đúng.<br> - Comment trong dashboard_stack.py các tài nguyên Glue, archive và analytics (Lambda/EventBridge + API).<br> - Giảm kích thước instance RDS (từ SMALL → MICRO) và cấu hình storage = 20GB. | 24/11/2025 | 24/11/2025 | |
| 3 | - Bắt đầu deploy AppStack, DashboardStack và DBInitStack phục vụ backend cho admin.<br> - Fix lỗi do cấu hình max AZ = 1 khi tạo RDS (AWS yêu cầu tối thiểu 2 AZ). Dù tạo 2 AZ nhưng không tạo Multi-AZ, chỉ tạo thêm subnet nên không phát sinh thêm cost.<br> - Refactor API: xử lý body trả về dạng string từ API Gateway, cập nhật endpoint path, cải thiện logging.<br> - Chỉnh CDK: dùng đúng secret cho Lambda, cập nhật VPC/subnet, thêm rule SG cho HTTPS, comment Bedrock endpoint không dùng.<br> - Cập nhật asset bundling (cp -r thay cp -au).<br> - Hệ thống lại nghiệp vụ admin: chỉ thao tác lịch hẹn, assign consultant vào slot, thống kê lịch hẹn trong ngày.<br> - Admin upload file SQL → ArchiveData lưu vào S3 → các lần deploy sau sẽ lấy từ S3 thay vì upload lại.<br> - Hướng phát triển: cho Lambda index.py đọc schema khi deploy, đọc data từ S3 trước, khả thi.<br> - Định hướng lưu toàn bộ data on-premise lên S3, Lambda xử lý để đẩy lên RDS khi deploy đầu tiên; cập nhật data mới sẽ do ArchiveData xử lý. | 25/11/2025 | 25/11/2025 | |
| 4 | - Hardcode schema trong index.py và xóa schema khỏi thư mục dự án.<br> - Xử lý dữ liệu mới và lưu CSV để dùng cho Athena DDL sau này.<br> - Thêm API và UI dashboard overview, refactor database admin.<br> - Thêm API thống kê tổng quan, khách hàng, tư vấn viên, lịch hẹn, chương trình cộng đồng; cập nhật UI dashboard để hiển thị các thông tin này.<br> - Refactor DatabasePage: bỏ chức năng chạy SQL thô, tập trung vào schema và thống kê.<br> - Update CDK + IAM role để dùng bucket S3 mới và phân quyền đúng.<br> - Tách toàn bộ business logic admin dashboard vào service class (code/services/admin.py).<br> - Đổi tên AdminStack → FrontendStack cho đúng vai trò; update toàn bộ reference. | 26/11/2025 | 26/11/2025 | |
| 5 | - Họp với team về chiến lược load data từ S3 lên RDS mỗi lần bật RDS.<br> - Yêu cầu: không phải lúc nào cũng load toàn bộ data cũ. Các data động (như lịch hẹn, lịch làm việc) thay đổi liên tục nên không thể luôn load lại toàn bộ.<br> - Giải pháp: giới hạn khối lượng data cần load. Data cố định (như thông tin consultant) thì load đầy đủ. Data thay đổi theo ngày (lịch hẹn) thì load theo điều kiện, ví dụ: thống kê lịch hẹn theo ngày admin cần xem.<br> - Hiện tại: cố định load data có thời gian trong khoảng trước – sau ngày hiện tại 1 ngày.<br> - Chỉnh lại vpc_stack để import S3 bucket tạo thủ công từ CLI.<br> - aws s3 mb s3://meetassist-data-<account-id>-ap-southeast-1 --region ap-southeast-1<br> - Dọn dẹp DashboardStack, bỏ code Glue & analytics cũ.<br> - Cập nhật API cho customer và consultant, thêm logging cho AdminManager Lambda. | 27/11/2025 | 27/11/2025 | |
| 6 | - Quản lý EventBridge rule cho ArchiveData Lambda (bật/tắt/kiểm tra trạng thái/invoke thủ công).<br><br>**Disable:** `aws events disable-rule --name MeetAssist-ArchiveSchedule`<br>**Enable:** `aws events enable-rule --name MeetAssist-ArchiveSchedule`<br>**Check status:** `aws events describe-rule --name MeetAssist-ArchiveSchedule`<br>**Invoke:** `aws lambda invoke --function-name DashboardStack-ArchiveData --payload "{}" --cli-binary-format raw-in-base64-out NUL`<br><br> - Xử lý lỗi CSV mở bằng Excel bị lỗi UTF-8, hiện Lambda index.py đang hỗ trợ cả UTF-8 và UTF-8 BOM.<br> - Tạo logic checksum cho ArchiveData nhằm tránh upload lại CSV không thay đổi → giảm PUT request trên S3.<br>   - **Hướng 1:** Không dùng checksum (ghi đè luôn). Dễ làm nhưng tốn chi phí và gây nhiễu timestamp.<br>   - **Hướng 2:** Dùng checksum (khuyến nghị): tính MD5, nếu giống thì bỏ qua, khác thì upload.<br> - Tạo file archive_info.json trong S3 để:<br>   - Theo dõi trạng thái archiving<br>   - Lưu checksum<br>   - Ghi lại thông tin số bản ghi, lỗi, thời gian cập nhật cuối<br>   - Có thể dùng cho dashboard trong tương lai<br> - Implement cơ chế Archive RDS → S3 với scheduled Lambda:<br>   - Tạo ArchiveService xử lý export CSV + upload S3 + metadata<br>   - Lambda archive_handler chạy theo lịch (5 phút, mặc định tắt)<br>   - Tự bỏ qua các bảng không thay đổi nhờ checksum<br>   - Update CDK để deploy Lambda + IAM + EventBridge rule<br>   - Cải thiện error handling cho nghiệp vụ consultant/appointment/program<br>   - Update dashboard_handler docstring để mô tả rõ cơ chế tách biệt CRUD và archiving | 28/11/2025 | 28/11/2025 | |

### Kết quả đạt được tuần 12:

* Refactor lại toàn bộ hệ thống backend & hạ tầng theo hướng tối ưu hơn và dễ maintain.
* Nắm rõ cách triển khai và cấu hình VPC, RDS, S3, Lambda, EventBridge bằng CDK.
* Hoàn thiện các API và UI dashboard phục vụ phần thống kê và quản trị.
* Tối ưu quy trình import data & archive data giữa RDS ↔ S3.
* Xây dựng cơ chế checksum giúp giảm cost S3 và tăng hiệu quả xử lý data.
* Tách biệt rõ business logic vào service class để dễ dàng test và mở rộng.
* Cải thiện logging, debugging và cấu trúc API Gateway – Lambda.
* Hoàn thiện process lưu trữ data on-premise lên cloud và xử lý khi deploy lại.
