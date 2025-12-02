---
title: "Event 1"
date: "2025-09-09"
weight: 1
chapter: false
pre: " <b> 4.1. </b> "
---


# Bài thu hoạch “AWS Cloud Mastery Series #1 - AI/ML/GenAI trên AWS”

### Mục Đích Của Sự Kiện

- Cung cấp tổng quan về các khả năng AI/ML/GenAI trên AWS và cách áp dụng chúng trong các trường hợp sử dụng thực tế.

### Danh Sách Diễn Giả

- **Lâm Tuấn Kiệt** – Sr DevOps Engineer, FPT Software  
- **Danh Hoàng Hiếu Nghị** – AI Engineer, Renova Cloud  
- **Đinh Lê Hoàng Anh** – Cloud Engineer Trainee, First Cloud AI Journey  
- **Văn Hoàng Kha** – Community Builder

### Nội Dung Nổi Bật

## 1. Generative AI trên Amazon Bedrock

**Foundation Models (FMs):**  
AWS cung cấp thư viện các mô hình nền tảng (FM) được quản lý hoàn toàn từ nhiều nhà cung cấp hàng đầu (Anthropic, OpenAI, Meta, v.v.), giúp người dùng tùy chỉnh cho nhiều tác vụ mà không cần tự huấn luyện mô hình từ đầu.

**Prompt Engineering:**  
Hiểu cách hướng dẫn mô hình thông qua nhiều kỹ thuật prompt:
  + **Zero-shot:** Mô hình chỉ nhận mô tả nhiệm vụ, không có ví dụ.  
  + **Few-shot:** Mô hình được cung cấp một vài ví dụ để học theo.  
  + **Chain-of-Thought:** Yêu cầu mô hình trình bày quy trình suy luận để tăng độ chính xác.

**Retrieval Augmented Generation (RAG):**  
Tăng chất lượng câu trả lời bằng cách bổ sung kiến thức bên ngoài:
  + **R – Retrieval:** Truy xuất thông tin liên quan từ kho dữ liệu.  
  + **A – Augmentation:** Thêm thông tin này vào prompt làm ngữ cảnh.  
  + **G – Generation:** Mô hình tạo câu trả lời chính xác và có căn cứ hơn.  
  + **Ứng dụng:** Chatbot theo ngữ cảnh, tìm kiếm nâng cao, tóm tắt dữ liệu theo thời gian thực.

**Amazon Titan Embeddings:**  
Mô hình embedding nhẹ, chuyển văn bản thành vector dùng trong tìm kiếm tương đồng và hệ thống RAG, hỗ trợ đa ngôn ngữ.

**AWS AI Services:** Các dịch vụ AI dựng sẵn:
  - Rekognition – Phân tích hình ảnh/video  
  - Translate – Dịch ngôn ngữ  
  - Textract – Trích xuất văn bản & bố cục từ tài liệu  
  - Transcribe – Chuyển giọng nói thành văn bản  
  - Polly – Chuyển văn bản thành giọng nói  
  - Comprehend – Phân tích ngôn ngữ tự nhiên  
  - Kendra – Tìm kiếm doanh nghiệp thông minh  
  - Lookout – Phát hiện bất thường  
  - Personalize – Gợi ý cá nhân hóa  

**Demo nổi bật:**  
Ứng dụng nhận diện khuôn mặt AMZPhoto minh họa cách tích hợp AI vào sản phẩm thực tế.

---

## 2. Amazon Bedrock AgentCore – Xây dựng AI Agents sẵn sàng cho môi trường sản xuất

Một framework mới hỗ trợ đội ngũ vận hành AI agent ở quy mô lớn:
  - Thực thi và mở rộng workflows của agent an toàn  
  - Quản lý bộ nhớ dài hạn  
  - Thiết lập quyền truy cập và danh tính chi tiết  
  - Tích hợp với Browser Tool, Code Interpreter, Memory Store  
  - Cung cấp quan sát, theo dõi và kiểm tra  
  - Hỗ trợ nhiều framework phổ biến (CrewAI, LangGraph, LlamaIndex, OpenAI Agents SDK, v.v.)

---

### Những Gì Học Được

- **Bedrock là trung tâm GenAI:** Truy cập dễ dàng nhiều mô hình nền tảng tại một nơi.  
- **Prompt + RAG để tùy chỉnh:** Cải thiện độ chính xác bằng ngữ cảnh và ví dụ.  
- **Embeddings giúp tìm kiếm thông minh hơn:** Titan Embeddings nâng cao chất lượng truy xuất thông tin.  
- **Dịch vụ AI dựng sẵn rút ngắn thời gian phát triển:** Giảm nhu cầu tự xây mô hình.  
- **AgentCore giảm độ phức tạp triển khai:** Quản lý scaling, memory, identity và monitoring.

---

### Ứng Dụng Vào Công Việc

- Các kiến thức về RAG và AgentCore phù hợp để áp dụng vào những dự án GenAI sắp tới của đội.  
- Hiểu rõ hơn các dịch vụ AI của AWS giúp lựa chọn công cụ chính xác cho từng nhu cầu ứng dụng.  
- Kinh nghiệm về prompt engineering có thể cải thiện độ chính xác trong nhiều mô hình AI.

### Trải nghiệm trong event

Tham gia workshop **“GenAI-powered App-DB Modernization”** là một trải nghiệm rất bổ ích, giúp tôi có cái nhìn toàn diện về cách hiện đại hóa ứng dụng và cơ sở dữ liệu bằng các phương pháp và công cụ hiện đại. Một số trải nghiệm nổi bật:

- Đạt thứ hạng 5 trong phần thi Kahoot cuối sự kiện và có chụp hình cùng các diễn giả.  
- Cùng mọi người tạo một nhóm nhỏ hợp tác mang tên **“Mèo Cam Đeo Khăn”**, kết hợp các thành viên từ “The Ballers” và “Vinhomies”.


#### Một số hình ảnh khi tham gia sự kiện
![Event Photo 1](/images/4-EventParticipated/4.1-Event1/kahoot.jpg)
![Event Photo 2](/images/4-EventParticipated/4.1-Event1/ending.jpg)
![Event Photo 3](/images/4-EventParticipated/4.1-Event1/meocam.jpg)
