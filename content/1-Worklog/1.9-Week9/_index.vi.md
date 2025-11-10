---
title: "Worklog Tuần 9"
date: "2025-09-09"
weight: 1
chapter: false
pre: " <b> 1.9. </b> "
---



### Mục tiêu tuần 9:

* Hoàn thiện kiến trúc chatbot sử dụng AWS Bedrock.
* Làm proposal chatbot và tính toán chi phí triển khai.
* Thành thạo Q Developer CLI để hỗ trợ sinh architecture diagram tự động.

### Các công việc cần triển khai trong tuần này:
| Thứ | Công việc                                                                                                                                                                   | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------ | --------------- | -------------- |
| 2   | - Cài Q Developer CLI để gen ra kiến trúc tự động.<br>- Đọc blog về chatbot sử dụng SQL và Bedrock.<br>- Họp với team đề xuất thay Lex + Translate bằng Custom Webhook + Bedrock để câu trả lời tự nhiên hơn. | 03/11/2025   | 03/11/2025      | [GitHub Sample](https://github.com/aws-samples/sample-Dynamic-Text-to-SQL-with-Amazon-Bedrock-Agent/blob/main/bin/agentic-text2sql.ts) |
| 3   | - Hoàn thiện kiến trúc tổng thể chatbot AWS.<br>- Tổ chức và lưu kiến trúc vào drive team.                                                                                  | 04/11/2025   | 04/11/2025      | [Drive Architecture](https://drive.google.com/drive/u/0/folders/1gkahOsw673lZPGN3CNM1mr5l34ZpCcOt) |
| 4   | - Làm chatbot Proposal.<br>- Tính toán chi phí dựa trên các dịch vụ AWS được sử dụng.                                                 | 05/11/2025   | 05/11/2025      | [AWS Pricing Calculator](https://calculator.aws/#/estimate) |
| 5   | - Soạn **draft proposal** cho chatbot.                                                                                               | 06/11/2025   | 06/11/2025      | |
| 6   | - Hoàn thiện proposal, cập nhật lên GitHub Page và nộp.                                                                              | 07/11/2025   | 07/11/2025      | |

### Kết quả đạt được tuần 9:

* Hoàn thành kiến trúc tổng thể cho chatbot sử dụng **AWS Bedrock**, **Lambda**, **API Gateway**, **S3**, và **Cognito**.
* Đề xuất hướng **Custom Webhook + Bedrock** thay cho Lex nhằm tăng tính tự nhiên và linh hoạt trong phản hồi.
* Sử dụng thành thạo **Q Developer CLI** để tự động sinh **architecture diagram**.
* Soạn thảo và hoàn thiện **proposal chatbot**, bao gồm phần **mô tả kỹ thuật** và **tính toán chi phí** qua **AWS Pricing Calculator**.
* Cập nhật và nộp **proposal chính thức** lên GitHub Page.
* Rút kinh nghiệm về cách thiết kế kiến trúc serverless, chi phí và sự khác biệt giữa Bedrock Agent với Lex.
