---
title: "Worklog Tuần 10"
date: "2025-09-09"
weight: 2
chapter: false
pre: " <b> 1.10. </b> "
---



### Mục tiêu tuần 10:

* Hoàn thiện các bước khởi tạo và triển khai hạ tầng chatbot.
* Tích hợp các dịch vụ AWS cần thiết cho hệ thống (CDK, Lambda, DynamoDB, Cognito, CloudFront...).

### Các công việc cần triển khai trong tuần này:
| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------ | --------------- | ----------------------------------------- |
| 2 | - Triển khai messenger webhook trên Meta Developers <br> - Bắt đầu giai đoạn 1 để triển khai chatbot bằng CDK | 10/11/2025 | 10/11/2025 | |
| 3 | - Test thử deploy local DB lên chatbot mẫu trên GitHub <br> - Test prompt tiếng Việt và cách bot phản hồi <br> - Một số prompt OK, một số bị timeout (đang điều tra nguyên nhân) | 11/11/2025 | 11/11/2025 | |
| 4 | - Chỉnh sửa lại architect, nối admin lambda vào thẳng DynamoDB trong RAG <br> - Code hạ tầng cơ bản ban đầu và cho Admin | 12/11/2025 | 12/11/2025 | |
| 5 | - Hoàn thiện frontend host trên S3 qua CloudFront + Route 53 <br> - Setup Cognito cho phía Admin | 13/11/2025 | 13/11/2025 | |
| 6 | - Nghiên cứu tự động hóa deploy frontend chung với hạ tầng bằng CDK (module S3 upload) <br> - Chỉnh sửa VPC stack <br> - Tìm hiểu JS Amplify vs dịch vụ AWS Amplify <br> - Vấn đề Glue Catalog & Lambda trong VPC <br> - Thêm Lambda ngoài VPC để invoke Glue Catalog/Crawler qua API Gateway | 14/11/2025 | 14/11/2025 | |


### Kết quả đạt được tuần 10:


* Bắt đầu giai đoạn 1 của chatbot bằng CDK.
* Kiểm thử deploy local DB lên chatbot mẫu, đánh giá hành vi bot khi dùng tiếng Việt.
* Phân tích lỗi timeout và giả định nguyên nhân do bot hiểu sai DB.
* Chỉnh sửa kiến trúc, bổ sung kết nối trực tiếp từ admin lambda vào DynamoDB.
* Hoàn thiện phần frontend qua S3 + CloudFront + Route 53 và thiết lập Cognito.
* Tìm hiểu cơ chế tự động hóa deploy frontend bằng CDK.
* Điều chỉnh lại VPC stack và làm rõ cách Amplify JS hoạt động so với dịch vụ AWS Amplify.
* Giải quyết bài toán Glue Catalog bằng cách thêm Lambda ngoài VPC để invoke qua API Gateway.
* Bổ sung Lambda xử lý Glue Crawler khi user gửi request.

