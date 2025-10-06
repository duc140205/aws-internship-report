---
title: "Worklog Tuần 4"
date: "2025-09-09"
weight: 1
chapter: false
pre: " <b> 1.4. </b> "
---



### Mục tiêu tuần 4:

* Hiểu sâu về **Identity & Security** trong hệ thống AWS:
  * Nắm được cách hoạt động của các dịch vụ quản lý truy cập như **IAM**, **Cognito**, **AWS Identity Center (SSO)** và **Organizations**.
  * Biết cách **mã hóa dữ liệu** bằng **AWS KMS** và áp dụng **Encrypt at rest** trong thực tế.

* Làm quen và thực hành **AWS Security Hub** để tổng hợp, đánh giá tiêu chuẩn bảo mật hệ thống.

* Hiểu rõ cơ chế **IAM Role, Condition key, và Permission Boundary**, ứng dụng trong việc giới hạn và kiểm soát quyền truy cập tài nguyên.

* Biết cách **phân tích và tối ưu chi phí giữa EC2 và Lambda** để lựa chọn dịch vụ phù hợp cho từng kịch bản.

* Rèn luyện kỹ năng **đọc hiểu và dịch tài liệu kỹ thuật AWS**, phục vụ cho việc tổng hợp kiến thức chuyên sâu và chia sẻ nội bộ.


### Các công việc cần triển khai trong tuần này:
| Thứ | Công việc                                                                                                                                                                                   | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu                            |
| --- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------ | --------------- | ----------------------------------------- |
| 2   | - Tìm hiểu các dịch vụ liên quan đến **Identity & Security** trong AWS: <br> &emsp; + **Amazon Cognito:** Dịch vụ xác thực, cấp phép, quản lý người dùng cho ứng dụng web & mobile.<br> &emsp;&emsp;• Tìm hiểu **User Pool** (đăng ký/đăng nhập người dùng) và **Identity Pool** (cấp quyền truy cập dịch vụ AWS khác).<br><br> &emsp; + **AWS Organizations:** Quản lý tập trung nhiều AWS Account, áp dụng **OU**, **Consolidated Billing** và **Service Control Policies (SCP)**.<br><br> &emsp; + **AWS Identity Center (SSO):** Quản lý quyền truy cập AWS Account & ứng dụng bên ngoài, tìm hiểu **Identity source** và **Permission Set**.<br><br> &emsp; + **AWS KMS:** Quản lý khóa mã hóa, tìm hiểu **CMK**, **Data Key** và cơ chế **Encryption at rest**.<br><br> - Thực hành các lab: <br> &emsp; + Lab 2: IAM Role ✅ <br> &emsp; + Lab 30: IAM Permission Boundary ✅ <br> &emsp; + Lab 27: Tag and Resource Groups ✅ <br> &emsp; + Lab 28: Quản lý EC2 qua Resource Tag <br> &emsp; + Lab 18: AWS Security Hub ✅ <br> &emsp; + Lab 12: AWS SSO (SUS) <br> &emsp; + Lab 33: KMS Workshop ✅ <br> &emsp; + Lab 44: IAM Role and Condition <br> &emsp; + Lab 48: IAM Role and Application <br> &emsp; + Lab 22 ✅ | 29/09/2025   | 29/09/2025      | [AWS Study Group YouTube Playlist](https://www.youtube.com/watch?v=pZ2fgEFK3Vs&list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i&index=152) |
| 3   | - **Tìm hiểu & thực hành AWS Security Hub:** <br> &emsp; + Kích hoạt Security Hub và tích hợp với các dịch vụ bảo mật khác (GuardDuty, Config, Inspector). <br> &emsp; + Kiểm tra và đánh giá các tiêu chuẩn bảo mật (CIS AWS Foundations Benchmark, PCI DSS, v.v). <br> &emsp; + Phân tích phát hiện (Findings) và cách xử lý cảnh báo bảo mật. <br><br> - **So sánh & tối ưu chi phí giữa EC2 và AWS Lambda:** <br> &emsp; + Phân tích mô hình tính phí giữa EC2 (theo thời gian chạy) và Lambda (theo request & thời lượng thực thi). <br> &emsp; + Đánh giá tình huống sử dụng phù hợp, lựa chọn dịch vụ hiệu quả chi phí hơn. <br><br> - **Quản lý truy cập EC2 bằng Resource Tag và AWS IAM:** <br> &emsp; + Tạo chính sách IAM dựa trên thẻ (Tag-based policy). <br> &emsp; + Giới hạn quyền truy cập tài nguyên EC2 theo Tag. <br> &emsp; + Thực hành kiểm tra và xác minh quyền truy cập. | 30/09/2025   | 30/09/2025      | [Get started with AWS Security Hub](https://www.notion.so/Get-started-with-AWS-Security-Hub-27ed1c243c6a80b98608e1ac3a8fbecd?pvs=21) <br> [Tối ưu chi phí EC2 và Lambda](https://www.notion.so/T-i-u-chi-ph-EC2-v-i-Lambda-27ed1c243c6a80859243ca434584246e?pvs=21) <br> [Quản lý truy cập EC2 qua Resource Tag](https://www.notion.so/Qu-n-l-truy-c-p-v-o-d-ch-v-EC2-Resource-Tag-v-i-AWS-IAM-27ed1c243c6a80b1abeff843655d0676?pvs=21) |
| 4   | - **Tìm hiểu IAM Role và Condition trong AWS IAM:** <br> &emsp; + Ôn lại khái niệm IAM Role và cách gán Role cho dịch vụ AWS (EC2, Lambda...). <br> &emsp; + Phân biệt các loại **Trust Policy** và **Permission Policy**. <br> &emsp; + Nghiên cứu **Condition key** trong IAM Policy để giới hạn quyền truy cập dựa trên điều kiện (như `aws:SourceIp`, `aws:RequestedRegion`, hoặc theo **Tag**). <br> &emsp; + Thực hành lab: cấu hình và kiểm tra IAM Role với điều kiện cụ thể. <br><br> - **Tìm hiểu cơ chế mã hóa dữ liệu “Encrypt at rest” với AWS KMS:** <br> &emsp; + Ôn lại khái niệm **CMK (Customer Managed Key)** và **Data Key**. <br> &emsp; + Thực hành mã hóa dữ liệu lưu trữ bằng AWS KMS trên S3/EC2. <br> &emsp; + Phân biệt giữa **Encryption at rest** và **Encryption in transit**. | 01/10/2025   | 01/10/2025      | [IAM Role Condition](https://www.notion.so/IAM-Role-Condition-280d1c243c6a80479047cffc35a67c50?pvs=21) <br> [Encrypt at rest with AWS KMS](https://www.notion.so/Encrypt-at-rest-with-AWS-KMS-27ed1c243c6a8018b6ccce2b7de75729?pvs=21) |
| 5   | - **Giới hạn quyền của User bằng IAM Permission Boundary:** <br> &emsp; + Ôn lại khái niệm **IAM Policy** và **Role-based Access Control (RBAC)**. <br> &emsp; + Tìm hiểu cách Permission Boundary hoạt động như một **giới hạn tối đa** cho quyền của IAM User hoặc Role. <br> &emsp; + Phân biệt giữa **IAM Policy thông thường** và **Permission Boundary Policy**. <br> &emsp; + Thực hành: tạo một User và gán Permission Boundary để giới hạn phạm vi hành động (ví dụ chỉ cho phép tạo EC2 trong region cụ thể). <br> &emsp; + Kiểm tra kết quả bằng AWS CLI và Console. | 02/10/2025   | 02/10/2025      | [Giới hạn quyền của User với IAM Permission Boundary](https://www.notion.so/GI-I-H-N-QUY-N-C-A-USER-V-I-IAM-PERMISSION-BOUNDARY-27ed1c243c6a801c9b71cb52135090fc?pvs=21) |
| 6   | - Dịch blog & tài liệu liên quan đến AWS / Cloud: <br> &emsp; + Dịch nội dung từ document 1: AWS recognized as Leader in 2024-25 Omdia Universe for Cloud Container Management & Services <br> &emsp; + Dịch nội dung từ document 2: AWS Savings Plans: How to Implement an Effective Chargeback Strategy <br> &emsp; + Dịch nội dung từ document 3: *AWS Weekly Roundup: Amazon S3 Express One Zone price cuts, Pixtral Large on Amazon Bedrock, Amazon Nova Sonic, and more (April 14, 2025) | 03/10/2025   | 03/10/2025      | [Google Doc 1](https://docs.google.com/document/d/1tIYmhfVruIrpmRvHdUgwRzxpMvA1cdvpShytAxsNreQ/edit?tab=t.0) <br> [Google Doc 2](https://docs.google.com/document/d/1w7ObsIEvyJNPV3RWgjmvAxLa3lZz3s3kpSJWGpyYV7U/edit?usp=sharing) <br> [Google Doc 3](https://docs.google.com/document/d/1l9fOfRkPtOaiZ2pZh3qPM5xkh1UxKkL0G3ihQA6S0LM/edit?usp=sharing) |                                                                                         | 15/08/2025   | 15/08/2025      | <https://cloudjourney.awsstudygroup.com/> |


### Kết quả đạt được tuần 4:

* Hoàn thành tìm hiểu và thực hành các **dịch vụ liên quan đến Identity & Security trong AWS**, bao gồm:
  * **Amazon Cognito** – Quản lý xác thực và cấp quyền người dùng cho ứng dụng web/mobile.
  * **AWS Organizations** – Quản lý tập trung nhiều tài khoản AWS, áp dụng OU, SCP và Consolidated Billing.
  * **AWS Identity Center (SSO)** – Quản lý truy cập vào nhiều AWS Account & ứng dụng bên ngoài.
  * **AWS KMS (Key Management Service)** – Quản lý khóa mã hóa, thực hành mã hóa dữ liệu *at rest*.
  * **AWS Security Hub** – Giám sát & đánh giá tiêu chuẩn bảo mật toàn hệ thống.
  * **IAM Permission Boundary** – Thiết lập giới hạn tối đa cho quyền người dùng/role.

* Hoàn thành các bài **lab thực hành bảo mật & quản lý truy cập**:
  * IAM Role và Condition ✅  
  * Permission Boundary ✅  
  * Security Hub ✅  
  * Tag-based Access Control trên EC2 ✅  
  * Encrypt at rest with AWS KMS ✅  

* Nắm vững khái niệm và ứng dụng của các chính sách trong AWS IAM:
  * **Trust Policy**, **Permission Policy**, và **Condition Key**.  
  * Áp dụng tag-based policy để giới hạn quyền truy cập tài nguyên theo điều kiện thực tế.

* Biết cách **đánh giá & tối ưu chi phí** giữa EC2 và Lambda, lựa chọn dịch vụ phù hợp tùy workload.

* Dịch và tổng hợp **3 tài liệu/blog chuyên sâu về AWS & Cloud**:
  * [Document 1 – AWS recognized as Leader in 2024-25 Omdia Universe](https://docs.google.com/document/d/1tIYmhfVrulrpmRvHdUgwRzxpMvA1cdvpShytAxsNreQ/edit?usp=sharing)
  * [Document 2 – AWS Savings Plans: Chargeback Strategy](https://docs.google.com/document/d/1w7ObsIEvyJNPV3RWgjmvAxLa3LZz3s3kpSJWGpyYV7U/edit?usp=sharing)
  * [Document 3 – AWS Weekly Roundup (April 14, 2025)](https://docs.google.com/document/d/1l9fOfRkPtOaiZ2pZh3qPM5xkh1UxKkL0G3ihQA6S0LM/edit?usp=sharing)

* Nâng cao khả năng **đọc – dịch – phân tích tài liệu kỹ thuật tiếng Anh** về AWS, giúp củng cố kiến thức nền tảng về Cloud Security.





