---
title : "Kích hoạt Bedrock Models"
date :  "2025-09-09" 
weight : 3
chapter : false
pre : " <b> 5.3. </b> "
---

## Kích hoạt Bedrock Models

Trước khi triển khai giải pháp, bạn cần kích hoạt các mô hình Amazon Bedrock cần thiết trong tài khoản AWS của mình.

### Các bước Kích hoạt Mô hình

1. **Tìm kiếm Amazon Bedrock** trong AWS Console
2. **Truy cập Model catalog** từ menu điều hướng bên trái
3. **Chọn tên mô hình tương ứng:**
   - Anthropic Claude 3.5 Sonnet
   - Anthropic Claude 3 Sonnet
   - Anthropic Claude 3 Haiku
   - Amazon Titan Embeddings G1 – Text
4. **Chọn "Open in playground"** và gửi một tin nhắn thử nghiệm để kích hoạt từng mô hình

{{% notice note %}}
Đảm bảo bạn kích hoạt tất cả bốn mô hình trong khu vực **ap-northeast-1 (Tokyo)** vì giải pháp được triển khai trong khu vực này.
{{% /notice %}}

### Xác minh

Sau khi kích hoạt các mô hình, bạn có thể xác minh chúng có thể truy cập được bằng cách kiểm tra phần "Model access" trong bảng điều khiển Amazon Bedrock. Tất cả bốn mô hình sẽ hiển thị trạng thái "Access granted".
