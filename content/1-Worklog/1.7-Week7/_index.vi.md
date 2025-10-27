---
title: "Worklog Tuần 7"
date: "2025-09-09"
weight: 1
chapter: false
pre: " <b> 1.7. </b> "
---


### Mục tiêu tuần 7:

* Tìm hiểu cách triển khai và tối ưu kiến trúc AWS cho dự án thực tế.  
* Ôn tập các kiến thức nền tảng AWS.  
* Thử nghiệm triển khai chatbot Text2SQL và đánh giá hướng mở rộng.  
* Phân tích bảo mật và logic xử lý dữ liệu database trong hệ thống.

---

### Các công việc cần triển khai trong tuần này:
| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | ---------- | ------------- | ---------------- | --------------- |
| 2 | - Tìm hiểu cách **down scale** cho dự án. <br> - Tìm hiểu cách **implement một architecture trên AWS** là như thế nào. <br> - Ghi nhận sự cố hi hữu: **AWS sập tại us-east-1**, ảnh hưởng đến nhiều hệ thống. | 20/10/2025 | 20/10/2025 | Nội bộ AWS, báo cáo sự cố AWS |
| 3 | - Ôn tập các kiến thức nền tảng AWS để chuẩn bị kiểm tra. | 21/10/2025 | 21/10/2025 | <https://cloudjourney.awsstudygroup.com/> |
| 4 | - Vẽ lại kiến trúc tổng thể, **estimate pricing** cho dự án. <br> - Lên **direction ban đầu cho chatbot** dự án. <br> - [Tài liệu Direction (Notion)](https://www.notion.so/295d23b23efb80bb9500e5cb3222414c?pvs=21) | 22/10/2025 | 22/10/2025 | Notion nội bộ |
| 5 | - Nghiên cứu **bảo mật và logic an toàn dữ liệu database**, tránh trường hợp user thao tác sai (update/insert/delete không hợp lệ). <br> - **Triển khai chatbot Text2SQL** dựa trên hướng dẫn của AWS Blog. <br> - [AWS Blog: Build an AI-powered Text-to-SQL Chatbot](https://aws.amazon.com/vi/blogs/database/build-an-ai-powered-text-to-sql-chatbot-using-amazon-bedrock-amazon-memorydb-and-amazon-rds/?utm_source=chatgpt.com) | 23/10/2025 | 23/10/2025 | AWS Blog |
| 6 | - Đọc hiểu **source code Text2SQL chatbot**. <br> - [Note họp trên Notion](https://www.notion.so/NOTE-h-p-298d23b23efb8072a6a3e1f67d5c640a?pvs=21) <br> - **Họp team:** làm rõ cách chatbot tương tác với database, các phương án bảo mật và **giới hạn quyền truy cập DB**. <br> - Đề xuất hướng thay thế **RAG bằng DynamoDB cache** để giảm chi phí so với OpenSearch. | 24/10/2025 | 24/10/2025 | Notion nội bộ, AWS Blog |

---

### Kết quả đạt được tuần 7:

* Hiểu rõ hơn về quy trình triển khai kiến trúc trên AWS và cách tối ưu tài nguyên (down scale).  
* Hoàn thành việc ôn tập các dịch vụ cơ bản AWS, củng cố kiến thức nền.  
* Vẽ lại sơ đồ kiến trúc dự án và xác định được chi phí ước tính.  
* Định hướng ban đầu cho chatbot Text2SQL (flow, logic, giới hạn quyền truy cập).  
* Thành công triển khai chatbot theo hướng dẫn của AWS Blog.  
* Phân tích và đề xuất giải pháp thay thế RAG bằng mô hình cache sử dụng DynamoDB để tiết kiệm chi phí.  
* Tăng cường nhận thức về bảo mật database và kiểm soát truy cập khi chatbot thao tác với dữ liệu.  