---
title: "Event 2"
date: "2025-09-09"
weight: 1
chapter: false
pre: " <b> 4.2. </b> "
---

# Báo cáo tổng kết: “AWS Cloud Mastery Series #2 – DevOps on AWS”

### Mục Đích Của Sự Kiện

- Giới thiệu về các dịch vụ DevOps trên AWS và cách thiết kế pipeline CI/CD.
- Khám phá các khái niệm về Infrastructure as Code (IaC) và các công cụ liên quan.
- Trình bày tổng quan về các workload dạng container trên AWS.
- Minh họa cách đạt được giám sát và quan sát hiệu quả bằng các dịch vụ gốc của AWS.

### Danh Sách Diễn Giả

- **Trương Quang Tình** – AWS Community Builder, Platform Engineer (TymeX)  
- **Bảo Huỳnh** – AWS Community Builder  
- **Nguyễn Khánh Phúc Thịnh** – AWS Community Builder  
- **Trần Đại Vĩ** – AWS Community Builder  
- **Huỳnh Hoàng Long** – AWS Community Builder  
- **Phạm Hoàng Quý** – AWS Community Builder  
- **Nghiêm Lê** – AWS Community Builder  
- **Đinh Lê Hoàng Anh** – Cloud Engineer Trainee, First Cloud AI Journey

### Nội Dung Nổi Bật

### **1. Xây dựng nền tảng DevOps**

Các diễn giả nhấn mạnh rằng DevOps không chỉ là một chức danh công việc mà quan trọng hơn là việc hình thành các thói quen giúp nâng cao hiệu quả triển khai:
- Tự động hóa các tác vụ lặp đi lặp lại  
- Chia sẻ kiến thức giữa các vai trò  
- Liên tục thử nghiệm và học hỏi  
- Theo dõi các kết quả đo lường được thay vì chỉ dựa vào giả định  

Các diễn giả cũng chia sẻ những sai lầm phổ biến mà người mới học DevOps thường gặp, như quá phụ thuộc vào tutorial mà không tự xây dựng dự án thực tế, hoặc so sánh bản thân với người khác thay vì tập trung vào sự tiến bộ đều đặn của chính mình.

---

### **2. Thực hành Infrastructure as Code**

Thay vì chỉ trung thành với một công cụ, các diễn giả đã so sánh nhiều phương pháp tiếp cận IaC:

- **CloudFormation** là công cụ template gốc của AWS  
- **CDK** dành cho lập trình viên thích viết hạ tầng bằng ngôn ngữ lập trình  
- **Terraform** phù hợp với các đội nhóm làm việc đa nền tảng đám mây  

Sự khác biệt giữa Stack, Construct, State file và các lớp trừu tượng được giải thích bằng các ví dụ thực tiễn.

Thông điệp quan trọng: hạ tầng được xây dựng lại bằng IaC sẽ *nhất quán và dễ bảo trì* hơn nhiều so với cấu hình thủ công.

---

### **3. Container và mô hình triển khai**

Phần này được trình bày từng bước, bắt đầu từ khái niệm Dockerfile và cách tạo image. Sau đó mở rộng sang các dịch vụ AWS:

- **ECR** để lưu trữ và quét image container  
- **ECS & EKS** để điều phối container  
- **App Runner** cho các đội nhóm muốn triển khai mà không cần quản lý cluster  

Phần so sánh giữa ECS và EKS giúp làm rõ khi nào nên sử dụng từng dịch vụ.

---

### **4. Giám sát và truy vết**

Phần cuối của sự kiện tập trung vào AWS CloudWatch và X-Ray:

- CloudWatch là trung tâm cho các chỉ số, dashboard, cảnh báo và log  
- X-Ray giúp trực quan hóa luồng request và xác định các điểm nghẽn độ trễ  

Các diễn giả nhấn mạnh rằng observability không phải là thứ bổ sung sau cùng mà phải được tích hợp ngay từ đầu trong kiến trúc hệ thống.

---
### Những Gì Học Được
- DevOps không chỉ là một chức danh công việc mà còn là một tư duy và tập hợp các thói quen giúp cải thiện việc triển khai phần mềm.
- Tự động hóa, chia sẻ kiến thức, liên tục thử nghiệm và đo lường kết quả là những yếu tố thiết yếu để thành công với DevOps.
- Việc sử dụng Infrastructure as Code (IaC) giúp hạ tầng nhất quán và dễ bảo trì hơn so với cấu hình thủ công.
- Việc lựa chọn công cụ IaC (CloudFormation, CDK, Terraform) nên dựa trên nhu cầu của đội nhóm và yêu cầu của dự án.
- Hiểu rõ sự khác biệt giữa các dịch vụ container của AWS (ECR, ECS, EKS, App Runner) giúp lựa chọn giải pháp phù hợp cho từng trường hợp sử dụng.
- Việc giám sát và quan sát (monitoring & observability) phải được tích hợp ngay từ đầu, không phải là bước bổ sung sau cùng, để đảm bảo hệ thống ổn định và phát hiện sự cố kịp thời.


### Ứng dụng vào công việc

#### Ví dụ: Dự án Chatbot AI trên AWS

Sau khi tham dự sự kiện, tôi sẽ lên kế hoạch áp dụng các kiến thức về DevOps và AWS vào một dự án xây dựng Chatbot AI nếu có cơ hội. Dưới đây là cách tôi dự định thực hiện:

- **Thiết kế pipeline CI/CD:** Sử dụng AWS CodePipeline để tự động hóa quá trình build, test và deploy chatbot lên môi trường production, đảm bảo mỗi lần cập nhật mã nguồn đều được kiểm thử và triển khai tự động.
- **Infrastructure as Code:** Sử dụng AWS CDK để định nghĩa toàn bộ hạ tầng (Lambda, API Gateway, DynamoDB, S3, IAM, v.v.) dưới dạng mã nguồn, giúp việc tái sử dụng và mở rộng hệ thống dễ dàng, nhất quán.

Nhờ áp dụng DevOps và các dịch vụ AWS, dự án chatbot AI có thể phát triển nhanh, triển khai liên tục, dễ bảo trì và mở rộng khi cần thiết.


### Trải nghiệm sự kiện
- Tham dự sự kiện đã giúp mình có cái nhìn thực tế hơn về cách các tổ chức hiện đại triển khai DevOps trên AWS.
- Các diễn giả không chỉ chia sẻ kiến thức lý thuyết mà còn cung cấp nhiều ví dụ thực tế, giúp mình hiểu rõ hơn về các công cụ như CloudFormation, CDK, Terraform cũng như cách vận hành và triển khai container trên AWS.
- Sự kiện cũng là dịp tuyệt vời để mình kết nối với các bạn cùng chí hướng và học hỏi thêm nhiều kinh nghiệm thực tế từ các diễn giả.
#### Một số hình ảnh sự kiện

