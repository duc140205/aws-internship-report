---
title: "Worklog Tuần 11"
date: "2025-09-09"
weight: 2
chapter: false
pre: " <b> 1.11. </b> "
---



### Mục tiêu tuần 11:

* Hoàn thiện và ổn định **luồng phân tích dữ liệu (Analytics)** bằng cách chuyển đổi từ Glue Crawler sang Athena DDL nhằm tối ưu chi phí và đơn giản hóa kiến trúc.
* Chuẩn hóa lại **hệ thống Lambda**, tách bạch vai trò giữa AdminManager và Analytics Lambda, đồng thời đảm bảo hoạt động ổn định khi query Athena và thao tác với RDS.
* Làm rõ cách hoạt động của **Amazon Cognito**, đặc biệt là cơ chế user pool và tính độc lập với database, để chuẩn bị cho bước tích hợp xác thực.
* Triển khai và hoàn thiện **frontend admin**, mock data và kết nối với backend để hình dung rõ luồng dữ liệu thực tế từ S3 → Athena → Dashboard.
* Đảm bảo hạ tầng nền tảng hoạt động tốt bằng việc deploy thành công **login page** thông qua CloudFront và thử nghiệm quy trình CDK/CloudFormation.

### Các công việc cần triển khai trong tuần này:
| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------ | --------------- | ----------------------------------------- |
| 2   | **Khởi động tuần làm việc**: Triển khai hạ tầng, tạo Glue và chạy GlueHandler ngoài VPC để crawl dữ liệu. Sau đó chỉnh sửa frontend và mock data nhằm hình dung luồng dữ liệu từ S3 → Glue/Athena → Dashboard admin. Tạm hoãn tích hợp Cognito để ưu tiên phần data pipeline. | 17/11/2025 | 17/11/2025 | |
| 3   | **Tái thiết kế Analytics**: Quyết định loại bỏ Glue để giảm phức tạp, chuyển sang Lambda + Athena DDL nhằm chủ động định nghĩa schema và query dữ liệu. Họp team và demo giao diện mẫu để xác định cách hiển thị data. Tìm hiểu sâu hơn về Cognito. | 18/11/2025 | 18/11/2025 |  |
| 4   | **Dọn dẹp & tái cấu trúc kiến trúc**: Xóa Glue DB, endpoint cho Athena; cập nhật AdminManager Lambda để chỉ insert dữ liệu vào RDS. Tạo mới Lambda Analytics chạy ngoài VPC để xử lý Athena. Cập nhật admin_stack, xử lý mất user pool, xóa Glue crawler và nghiên cứu Athena DDL vs Glue. | 19/11/2025 | 19/11/2025 |  |
| 5   | **Chi tiết hóa Athena DDL & Cognito**: Tìm hiểu chuyên sâu cách define schema thủ công với DDL — linh hoạt, miễn phí, real-time. Ghi rõ về việc Cognito hoạt động độc lập, không phụ thuộc DB. Viết note lên Jira về thử nghiệm deploy domain bằng CDK. | 20/11/2025 | 20/11/2025 | |
| 6   | **Deploy Frontend Dashboad with Cognito**: Họp team và deploy thành công login page thông qua CloudFront (chưa dùng Route 53). Hoàn thiện xử lý logic của `admin_handler` để admin có thể insert dữ liệu vào RDS qua frontend. | 21/11/2025 | 21/11/2025 | |

### Kết quả đạt được tuần 11:


* Triển khai hạ tầng ban đầu và thử nghiệm Glue + Lambda catalog.
* Thay đổi hướng Analytics, chuyển hoàn toàn sang Athena DDL.
* Xóa Glue DB, crawler, endpoint và tối ưu lại kiến trúc.
* Khởi tạo Lambda Analytics mới để query Athena ngoài VPC.
* Hiểu rõ hơn về cách Cognito hoạt động độc lập với database.
* Hoàn thành deploy login page trên CloudFront.
* Hoàn thiện logic lambda admin_handler để insert data vào RDS.
