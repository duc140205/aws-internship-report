---
title: "Bản đề xuất"
date: "2025-09-09"
weight: 2
chapter: false
pre: " <b> 2. </b> "
---



# AI-Powered Booking Chatbot on AWS
## Giải pháp AWS Serverless tích hợp RAG cho đặt lịch và chăm sóc khách hàng

### 1. Tóm tắt điều hành  
AI-Powered Booking Chatbot on AWS là giải pháp chatbot thông minh được thiết kế nhằm hỗ trợ người dùng trong việc đặt lịch và tra cứu thông tin dịch vụ thông qua Facebook Messenger. Hệ thống kết hợp giữa cơ chế **RAG (Retrieval-Augmented Generation)** và **mô hình SQL-Driven** để vừa xử lý hội thoại tự nhiên, vừa truy xuất dữ liệu chính xác từ cơ sở dữ liệu PostgreSQL.
 Nền tảng sử dụng kiến trúc **AWS Serverless** giúp giảm thiểu chi phí vận hành, tự động mở rộng, và đảm bảo độ tin cậy.   

### 2. Tuyên bố vấn đề  
*Vấn đề hiện tại*  
Các hệ thống đặt lịch truyền thống thường yêu cầu thao tác thủ công hoặc web-based, thiếu khả năng trò chuyện tự nhiên và phản hồi theo ngữ cảnh. Việc triển khai chatbot AI có thể phức tạp nếu không có nền tảng đám mây linh hoạt để quản lý dữ liệu, intent, và bảo mật.


*Giải pháp*  
Dự án áp dụng AWS Lambda, API Gateway, DynamoDB, PostgreSQL, và các dịch vụ hỗ trợ AI để tạo nên chatbot đa năng có khả năng:
  - Phân tích intent hội thoại (đặt lịch, tư vấn, câu hỏi chung).
  - Kết nối cơ sở dữ liệu để truy xuất lịch, thông tin khách hàng, hoặc dữ liệu phân tích.
  - Hỗ trợ mô-đun RAG cho các câu hỏi mở hoặc ngữ cảnh phức tạp.
  - Cung cấp giao diện quản trị (Admin Dashboard) giúp theo dõi lịch sử hội thoại, thống kê và hiệu năng hệ thống.
 

*Lợi ích và hoàn vốn đầu tư (ROI)*  
Giải pháp giúp tiết kiệm chi phí vận hành (so với hạ tầng on-premise), đồng thời tạo môi trường học tập thực tế cho sinh viên/nhóm nghiên cứu về AWS Serverless, NLP và RAG. Hệ thống có thể tái sử dụng và mở rộng để áp dụng cho các doanh nghiệp vừa và nhỏ trong tương lai.
  

### 3. Kiến trúc giải pháp  
**Mô tả tổng quan**:
Nền tảng hoạt động theo mô hình Serverless + VPC-secured, trong đó toàn bộ xử lý hội thoại, lịch đặt, và dữ liệu AI đều chạy trên AWS Lambda và dịch vụ không máy chủ

![Chatbot Architecture](/images/2-Proposal/chatbot_final_final.drawio.png)

*Luồng dữ liệu chính*
1. Người dùng trò chuyện qua Facebook Messenger → **API Gateway** → **Lambda WebhookReceiver**.

2. **Lambda ChatOrchestrator** xử lý intent, gọi Intent Model hoặc RAG Module.

3. **DynamoDB** lưu cache hội thoại và metadata, trong khi **PostgreSQL** lưu lịch sử và thông tin đặt lịch.

4. **EventBridge** quản lý tác vụ lưu data sau 1 ngày đặt lịch trong db lại về s3 để phục vụ cho Dashboard Admin


5. **Admin Dashboard** (Route 53 + Cloudfront + S3 + Cognito) giúp admin theo dõi, kiểm thử và quản lý hệ thống.


*Dịch vụ AWS sử dụng*  
- *AWS Lambda*: Xử lý hội thoại, điều phối intent, lập lịch.

- *Amazon API Gateway*: Kết nối với Messenger và Admin Dashboard.

- *Amazon DynamoDB*: Lưu cache, logs, metadata cho RAG.

- *Amazon RDS (PostgreSQL)*: Lưu thông tin đặt lịch, lịch sử tương tác.

- *Amazon EventBridge*: Quản lý sự kiện, cron job.

- *Amazon S3 + CloudFront + Route 53*: Lưu trữ và phân phối giao diện quản trị.

- *Amazon Cognito*: Quản lý người dùng và phân quyền Admin.

- *AWS Secrets Manager*: Lưu trữ thông tin xác thực dịch vụ bảo mật.

- *AWS Glue + Athena* (phân tích tùy chọn): Trích xuất và phân tích dữ liệu lịch sử hội thoại.



### 4. Triển khai kỹ thuật  
*Các giai đoạn triển khai*  
Dự án gồm 2 phần — xây dựng hệ thống chatbot và nền tảng quản trị AI Booking — mỗi phần trải qua 4 giai đoạn chính:

1. *Nghiên cứu và thiết kế kiến trúc*  
   - Phân tích các mô hình chatbot tích hợp RAG (Retrieval-Augmented Generation) và intent classification.  
   - Đề xuất kiến trúc AWS Serverless phù hợp: Lambda, API Gateway, RDS PostgreSQL, DynamoDB, EventBridge.  
   - Nghiên cứu mô hình CI/CD với AWS CDK hoặc CloudFormation để triển khai tự động.  
   - (Thực hiện trước giai đoạn workshop — chuẩn bị môi trường kỹ thuật và sơ đồ kiến trúc.)

2. *Tính toán chi phí và kiểm tra tính khả thi*  
   - Sử dụng AWS Pricing Calculator để ước tính chi phí hạ tầng (Lambda, RDS, DynamoDB, Amplify, Cognito, EventBridge, S3, CloudFront).  
   - Thực hiện thử nghiệm nhỏ trên môi trường sandbox để kiểm chứng khả năng mở rộng, thời gian phản hồi và độ ổn định.  
   - (Giai đoạn đầu workshop — dùng kết quả để tinh chỉnh tài nguyên và định cỡ chi phí.)

3. *Điều chỉnh kiến trúc và tối ưu giải pháp*  
   - Cân đối chi phí và hiệu năng: tối ưu hóa số lượng Lambda, giảm chi phí RDS bằng caching (DynamoDB).  
   - Xây dựng cơ chế phân tách luồng hội thoại giữa intent “Booking” và “Customer Service” để giảm overhead xử lý.  
   - Kiểm thử khả năng mở rộng khi tăng số lượng người dùng đồng thời.  
   - (Giữa giai đoạn workshop — đảm bảo hệ thống đạt hiệu quả chi phí và kỹ thuật tối ưu.)

4. *Phát triển, kiểm thử và triển khai*  
   - Phát triển các Lambda chính: WebhookReceiver, ChatOrchestrator, RAG Module; tích hợp RDS và DynamoDB.  
   - Cấu hình API Gateway, EventBridge và Cognito; xây dựng giao diện quản trị bằng JavaScript.  
   - Kiểm thử end-to-end: Messenger → API Gateway → Chatbot → Database → Dashboard.  
   - (Cuối workshop — đưa hệ thống vào vận hành, ghi nhận kết quả và demo hoàn chỉnh.)  

*Yêu cầu kỹ thuật*  
- Nền tảng chính: AWS Serverless (Lambda, API Gateway, DynamoDB, RDS PostgreSQL, EventBridge).  
- Bảo mật: Amazon Cognito, AWS Secrets Manager, IAM Role tách biệt.  
- Phát triển: AWS CDK/SDK, JavaScript cho giao diện quản trị.  
- Kết nối ngoài: Facebook Messenger Webhook (API Gateway endpoint).  
- Tự động hóa: CloudFormation template.

### 5. Lộ trình & Mốc triển khai   
- *Thực tập (Tháng 9–12)*:  
    - Tháng 9: Học AWS củng cố kiến trúc serverless, xây dựng prototype.
    - Tháng 10: Thiết kế và điều chỉnh kiến trúc.  
    - Tháng 11: Phát triển và kiểm thử hệ thống.
    - Tháng 12: Triển khai hoàn chỉnh, demo và đánh giá kết quả. 
- *Sau triển khai*: Nghiên cứu thêm trong vòng 1 năm.  

### 6. Ước tính ngân sách  

- Tải xuống báo cáo ước tính ngân sách (PDF): [Ước tính ngân sách - PDF](/images/2-Proposal/chatbotestimation.pdf).  
  
 
### 7. Đánh giá rủi ro

| Rủi ro | Ảnh hưởng | Xác suất | Giảm thiểu |
|---|---:|---:|---|
| Messenger webhook gián đoạn | Trung bình | Trung bình | Thiết lập retry & log monitoring qua CloudWatch. |
| Sai phân quyền Lambda | Cao | Thấp | Sử dụng IAM Role riêng và kiểm thử quyền tối thiểu. |
| Tắc nghẽn dữ liệu DynamoDB | Trung bình | Thấp | Giới hạn TTL và cache cục bộ. |
| Vượt chi phí | Trung bình | Trung bình | Giám sát AWS Billing Alerts, bật Budget notification. |

### 8. Kết quả kỳ vọng  
- *Kỹ thuật*: Hoàn thiện chatbot AI có thể đặt lịch qua Messenger, tự động phản hồi câu hỏi khách hàng.
- *Học thuật*: Thành viên workshop hiểu quy trình thiết kế kiến trúc AWS Serverless có tích hợp RAG.
- *Thực tế*: Mở rộng mô hình thành chatbot doanh nghiệp, kết hợp phân tích dữ liệu hội thoại bằng Glue & Athena.
- *Giá trị dài hạn*: Tạo tiền đề cho nền tảng Customer Service AI nội bộ hoặc sản phẩm SaaS tương tự.