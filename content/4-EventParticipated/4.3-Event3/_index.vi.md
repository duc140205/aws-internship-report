---
title: "Event 3"
date: "2025-09-09"
weight: 1
chapter: false
pre: " <b> 4.3. </b> "
---


# Bài thu hoạch: “AWS Cloud Mastery Series #3: AWS Well-Architected – Security Pillar Workshop”

### Mục Tiêu Sự Kiện
Workshop tập trung vào Security Pillar của AWS Well-Architected Framework, cung cấp một lộ trình toàn diện về 5 lĩnh vực bảo mật quan trọng:

- Trụ cột 1: Identity & Access Management (IAM)
- Trụ cột 2: Detection & Continuous Monitoring
- Trụ cột 3: Infrastructure Protection
- Trụ cột 4: Data Protection
- Trụ cột 5: Incident Response

Sự kiện cũng giới thiệu về AWS Cloud Clubs và các hoạt động cộng đồng hỗ trợ người học cloud tại các trường đại học.

### Diễn Giả

- **Lê Vũ Xuân An** - AWS Cloud Club Captain HCMUTE  
- **Trần Đức Anh** - AWS Cloud Club Captain SGU  
- **Trần Đoàn Công Lý** - AWS Cloud Club Captain PTIT  
- **Danh Hoàng Hiếu Nghị** - AWS Cloud Club Captain HUFLIT  

- **Huỳnh Hoàng Long** - AWS Community Builders  
- **Đinh Lê Hoàng Anh** - AWS Community Builders  

- **Nguyễn Tuấn Thịnh** - Cloud Engineer Trainee  
- **Nguyễn Đỗ Thành Đạt** - Cloud Engineer Trainee  

- **Văn Hoàng Kha** - Cloud Security Engineer, AWS Community Builder  

- **Thịnh Lâm** - FCJ Member  
- **Việt Nguyễn** - FCJ Member  

- **Mendel Grabski (Long)** - Ex-Head of Security & DevOps, Cloud Security Solution Architect  
- **Trịnh Trương** - Platform Engineer tại TymeX, AWS Community Builder  

### Các Điểm Nổi Bật

#### Giới Thiệu AWS Cloud Club
Sự kiện mở đầu bằng phần giới thiệu về sáng kiến AWS Cloud Club:
- Nền tảng giúp phát triển kỹ năng cloud qua các tình huống thực tế  
- Cơ hội nhận mentorship từ các chuyên gia AWS  
- Xây dựng cộng đồng và kết nối giữa sinh viên  
- Hỗ trợ bởi nhiều club như HCMUTE, SGU, PTIT và HUFLIT  

Thông điệp chính: Cloud Clubs giúp sinh viên phát triển kỹ năng, nghề nghiệp và các mối quan hệ chuyên môn.

#### Identity & Access Management (IAM)
IAM là một chủ đề trọng tâm của workshop. Các điểm chính:

- Áp dụng nguyên tắc Least Privilege  
- Xóa root access keys sau khi thiết lập ban đầu  
- Tránh wildcard permission (*)  
- Sử dụng AWS SSO để quản lý quyền tập trung trong môi trường multi-account  
- Hiểu rõ SCPs – bộ giới hạn permission cấp tổ chức  
- Sử dụng Permission Boundaries để giới hạn phạm vi quyền của user/role  

Hai phương thức MFA – TOTP và FIDO2 – được so sánh chi tiết về tính bảo mật và khả năng phục hồi.

Secrets Manager và quy trình xoay vòng credential (create → set → test → finalize) cũng được nhấn mạnh như một best practice quan trọng.

#### Detection & Continuous Monitoring
Phần này trình bày cách AWS xây dựng khả năng quan sát đa lớp:

- Management Events: API calls, thay đổi cấu hình  
- Data Events: hành động ở mức object trên S3, log thực thi Lambda  
- Network Events: VPC Flow Logs  
- Quan sát đồng nhất trên toàn bộ tài khoản trong tổ chức  

EventBridge được nói đến nhiều trong việc cảnh báo và tự động hóa — đặc biệt khả năng định tuyến sự kiện liên tài khoản để tạo nên security workflow tập trung.

Khái niệm “Detection-as-Code” được trình bày thông qua CloudTrail Lake và triển khai IaC cho detection logic.

#### Amazon GuardDuty
GuardDuty được giới thiệu là dịch vụ phát hiện mối đe dọa liên tục, dựa trên phân tích:

- CloudTrail events  
- VPC Flow Logs  
- DNS queries  

Giúp xác định hành vi như tắt logging, lưu lượng bất thường hoặc truy vấn tên miền độc hại.

Các tính năng nâng cao: quét malware S3, giám sát audit log EKS, phát hiện bất thường RDS, phân tích network của Lambda, và runtime protection qua GuardDuty Agent.

GuardDuty được liên hệ với các framework như AWS Foundational Security Best Practices và CIS Benchmarks.

#### Network Security Controls
Phần bảo vệ hạ tầng bao gồm:

- Phân loại tấn công: Ingress, Egress, Insider  
- Khác biệt SG (stateful) và NACLs (stateless)  
- Route 53 Resolver cho môi trường hybrid  
- AWS Network Firewall: lọc egress, segmentation, IDS/IPS  
- Tích hợp threat intel của GuardDuty để tự động chặn  

#### Data Protection & Governance
Các điểm chính về mã hóa và quản lý credential:

- Cấu trúc KMS (CMK → Data Key)  
- Sử dụng IAM conditions để kiểm soát hoạt động mã hóa  
- ACM cho chứng chỉ miễn phí + tự động gia hạn  
- Secrets Manager rotation  
- Bắt buộc TLS khi truy cập S3 & DynamoDB  
- Cấu hình SSL/TLS cho RDS  

#### Incident Response & Prevention
**Best Practices phòng ngừa:**

- Sử dụng temporary credentials  
- Không public trực tiếp S3 buckets  
- Đặt các service nhạy cảm trong private subnet  
- Dùng IaC để đảm bảo consistency  
- Quy trình phê duyệt 2 lớp cho thay đổi rủi ro cao  

**Quy trình IR 5 bước:**  
Chuẩn bị → Phát hiện & Phân tích → Cô lập → Xóa bỏ & Khôi phục → Rút kinh nghiệm.

### Ứng Dụng Vào Công Việc
Các khái niệm bảo mật từ workshop áp dụng trực tiếp vào dự án AI Chatbot của nhóm. IAM giúp kiểm soát truy cập tốt hơn cho backend và admin tool. Logging, monitoring và bảo vệ hạ tầng giúp chúng tôi xây dựng pipeline giám sát rõ ràng, tránh cấu hình sai. Quy trình ứng phó sự cố giúp nhóm phản ứng nhanh và nhất quán hơn. Tất cả góp phần xây dựng nền tảng chatbot ổn định và an toàn hơn.

### Trải Nghiệm Sự Kiện
- Sự kiện được tổ chức tốt, diễn giả truyền đạt rõ ràng những chủ đề phức tạp.  
- Phần hỏi đáp giúp người tham gia củng cố hiểu biết và giải đáp thắc mắc.

#### Một Số Hình Ảnh
![Event Photo 1](/images/4-EventParticipated/4.3-Event3/1.jpg)  
![Event Photo 2](/images/4-EventParticipated/4.3-Event3/2.jpg)  
![Event Photo 3](/images/4-EventParticipated/4.3-Event3/3.jpg)
