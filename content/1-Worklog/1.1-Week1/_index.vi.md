---
title: "Worklog Tuần 1"
date: "2025-09-09"
weight: 1
chapter: false
pre: " <b> 1.1. </b> "
---



### Mục tiêu tuần 1:

* Làm quen với các thành viên trong chương trình **First Cloud Journey (FCJ)** và nắm được nội quy, quy định tại đơn vị thực tập.  
* Hiểu khái niệm cơ bản về **điện toán đám mây** và hệ sinh thái dịch vụ AWS (Compute, Storage, Networking, Database, Security…).  
* Thực hành khởi tạo và quản lý tài khoản AWS Free Tier theo **best practice**: IAM User, Group, Role; hạn chế dùng root account; thiết lập Budget theo dõi chi phí.  
* Sử dụng song song **AWS Management Console** và **AWS CLI** để thao tác với tài nguyên, đồng thời làm quen với scripting để tự động hóa.  
* Nắm cơ chế **tối ưu hóa chi phí**: Spot Instance, AWS Pricing Calculator, Budget/Cost Budget.  
* Làm quen khái niệm **Serverless** (Lambda, DynamoDB) và công cụ **Hugo** để triển khai workshop/web tĩnh.  
* Hiểu và thực hành cơ bản về **Networking trong AWS**: VPC, Subnet, Route Table, Security Group, NACL, IGW, NAT GW, VPC Endpoint, VPC Flow Logs, VPN, Direct Connect, Elastic Load Balancing.

### Các công việc cần triển khai trong tuần này:
| Thứ | Công việc                                                                                                                                                                                   | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu                            |
| --- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------ | --------------- | ----------------------------------------- |
| 2   | - Làm quen với các thành viên FCJ <br> - Đọc và lưu ý các nội quy, quy định tại đơn vị thực tập  <br> - Tìm hiểu tổng quan về điện toán đám mây Module 01 - 01 → 07: Tổng quan cơ bản về AWS, tìm hiểu về hạ tầng của AWS, chính sách của AWS, AWS Services, quản lý cũng như tối ưu hóa chi phí thông qua Budget, contact với AWS.   <br>- **Thực hành:** <br>&emsp; + Tạo AWS account Free Tier <br>&emsp; + Cài đặt AWS CLI & cấu hình <br>&emsp; + Tạo IAM User, Group, Role để quản lý tài khoản AWS thay vì dùng root account <br>&emsp; + Setup Budget, Cost Budget để quản lý Credit monthly <br> - Nhận biết cách yêu cầu hỗ trợ từ đội ngũ AWS thông qua AWS Support   | 08/09/2025   | 08/09/2025      |   <https://000001.awsstudygroup.com/> <br>  <https://000007.awsstudygroup.com/> <br>  <https://000009.awsstudygroup.com/> |
| 3   | - Tìm hiểu về Hugo để làm workshop AWS, cách cài đặt môi trường, xây dựng cấu trúc và khởi chạy trang web <br> - Hoàn thành các Lab của Module 1 <br> - Tìm hiểu rõ hơn về tối ưu hóa chi phí qua Spot Instance (-90% chi phí, nhưng có thể bị thu hồi tài nguyên) <br> - Hiểu khái niệm **Serverless** (không quản lý server, ví dụ Lambda, DynamoDB) <br> - Sử dụng AWS Pricing Calculator: ước lượng, chia sẻ, so sánh giá theo region <br> - Dịch vụ mạng: Amazon VPC, VPC Peering, Transit Gateway, VPN, Direct Connect, Elastic Load Balancing <br> - **Kiến thức chính:** VPC = mạng ảo riêng trong 1 Region, chia subnet theo AZ, kiểm soát bằng Route Table + Security (SG, NACL)                                            | 09/09/2025   | 09/09/2025      | <https://van-hoang-kha.github.io/> |
| 4   | - Thực hành Lab IAM Role <br>&emsp; + Tạo & quản lý IAM Group, User, Role <br>&emsp; + Gán policy trực tiếp & inline policy <br>&emsp; + Đăng nhập bằng IAM User, chuyển đổi IAM Role <br> - Tìm hiểu VPC cơ bản: Subnet (public/private), Route Table, IGW, NAT GW <br> - Elastic Network Interface (ENI), Elastic IP (EIP) <br> - VPC Endpoint (Interface & Gateway) <br> - Security Group (stateful) vs NACL (stateless) <br> - VPC Flow Logs (CloudWatch / S3) <br> - VPC Peering & hạn chế <br> - Transit Gateway & Attachment <br> - Hoàn thành Module 02 - 01 → 02 | 10/09/2025   | 10/09/2025      | <https://cloudjourney.awsstudygroup.com/> |
| 5   | - VPN Site-to-Site (Virtual Private Gateway & Customer Gateway) <br> - VPN Client-to-Site cơ bản <br> - AWS Direct Connect (Hosted/Dedicated Connections) <br> - Elastic Load Balancing (ELB): ALB, NLB, CLB, GLB <br>&emsp; + Health check, Sticky session, Access logs <br>&emsp; + Path-based routing, target types <br> - Hoàn thành Module 02 - 03                  | 11/09/2025   | 11/09/2025      | <https://cloudjourney.awsstudygroup.com/> |
| 6   | - Ôn tập các kiến thức đã học trong tuần (VPC, Subnet, IAM, Security, ELB…) <br> - Thực hành Lab nâng cao về AWS VPC <br> - Làm quen Route 53 Resolver (Hybrid DNS) <br> - Thực hành VPC Peering                                                                                         | 12/09/2025   | 14/09/2025      | [Note tổng hợp](https://www.notion.so/C-c-t-c-n-ghi-nh-26ad1c243c6a80159943e7d394e4ca40?pvs=21) <br> [AWS VPC](https://www.notion.so/M-i-tr-ng-AWS-VPC-26bd1c243c6a80ceab10c980d039587d?pvs=21) <br> [Route 53 Resolver](https://www.notion.so/Thi-t-l-p-Hybrid-DNS-v-i-Route-53-Resolver-26dd1c243c6a8001ad9cf56de336df6b?pvs=21) <br> [VPC Peering](https://www.notion.so/Thi-t-l-p-VPC-Peering-26ed1c243c6a8070af32e2113871d9a9?pvs=21) |


### Kết quả đạt được tuần 1:

- **Kiến thức nền tảng về AWS**
  - Hiểu AWS là gì, nắm được các nhóm dịch vụ cơ bản: Compute, Storage, Networking, Database, Security…
  - Nhận biết sự khác biệt giữa **AWS Management Console**, **AWS CLI** và **AWS SDK**.

- **Thực hành với AWS Free Tier**
  - Tạo và cấu hình tài khoản AWS Free Tier thành công.
  - Cài đặt và cấu hình AWS CLI (Access Key, Secret Key, Region mặc định).
  - Quản lý tài nguyên AWS song song qua **Console (Web)** và **CLI**.

- **Kỹ năng sử dụng AWS CLI**
  - Kiểm tra thông tin tài khoản & cấu hình.
  - Lấy danh sách Region khả dụng.
  - Làm việc với EC2: xem instance, tạo & quản lý key pair, kiểm tra dịch vụ đang chạy.
  - Nắm cách viết script cơ bản để tự động hóa thao tác.

- **IAM (Identity and Access Management)**
  - Tạo & quản lý IAM User, Group, Role.
  - Gán policy trực tiếp và inline policy.
  - Đăng nhập bằng IAM User và thực hành chuyển đổi Role.
  - Nhận thức tầm quan trọng của việc không dùng root account.

- **Tối ưu hóa chi phí AWS**
  - Hiểu cơ chế **Spot Instance** (giảm ~90% chi phí, nhưng có thể bị reclaim).
  - Thực hành tạo **Budget** và **Cost Budget** để theo dõi Credit.
  - Sử dụng **AWS Pricing Calculator** để ước lượng chi phí, chia sẻ & so sánh theo region.

- **Serverless & Workshop**
  - Hiểu khái niệm **Serverless**: Lambda, DynamoDB, dịch vụ không cần quản lý server.
  - Làm quen với **Hugo** để dựng workshop/trang web tĩnh trên AWS.

- **Networking trong AWS**
  - Hiểu khái niệm **VPC (Virtual Private Cloud)**: mạng ảo riêng trong 1 Region.
  - Phân biệt **Subnet public/private**, Route Table, IGW, NAT GW.
  - Tìm hiểu Elastic IP, ENI, VPC Endpoint, VPC Flow Logs.
  - So sánh Security Group (stateful) và NACL (stateless).
  - Nắm được VPC Peering, Transit Gateway và hạn chế.
  - Làm quen VPN Site-to-Site, VPN Client, AWS Direct Connect.
  - Hiểu các loại **Elastic Load Balancer (ALB, NLB, CLB, GLB)**.

---

✅ Sau tuần 1, đã có nền tảng vững về:
- Quản lý tài khoản AWS an toàn (IAM, Budget).
- Sử dụng CLI/Console để thao tác với dịch vụ AWS.
- Nắm cơ bản về Networking (VPC, Subnet, VPN, ELB).
- Hiểu các phương thức tối ưu hóa chi phí.
- Sẵn sàng cho các lab nâng cao (Route 53, Peering, Hybrid DNS, …).


### Reflection – Đánh giá bản thân và khó khăn gặp phải trong tuần 1

- **Điểm mạnh đạt được:**
  - Nắm rõ khái niệm cơ bản về AWS và cách quản lý tài nguyên bằng nhiều phương thức (Console, CLI, SDK).
  - Làm chủ được các thao tác khởi tạo, cấu hình tài khoản và IAM theo best practice (không dùng root account).
  - Có cái nhìn hệ thống hơn về cách AWS tổ chức dịch vụ, đặc biệt là nhóm Networking.

- **Khó khăn gặp phải:**
  - Ban đầu còn nhầm lẫn giữa AWS CLI và SDK → sau khi thực hành đã phân biệt rõ vai trò từng công cụ.
  - VPC và các khái niệm liên quan (subnet, CIDR, NACL, Security Group) hơi phức tạp, dễ rối khi vừa đọc lý thuyết vừa làm lab.
  - Trong quá trình tạo **Budget Usage** chưa thấy lựa chọn `EC2:Running Hours` → khả năng do tài khoản mới chưa có dữ liệu thực tế.
  - Việc tính toán chi phí với **Pricing Calculator** ban đầu hơi khó ước lượng do chưa quen chọn đúng loại dịch vụ và region.
  - Khi làm **các lab nâng cao** (VPC Peering, Route 53 Resolver, Hybrid DNS…), gặp khá nhiều khó khăn vì lần đầu tiếp xúc với hệ thống thực tế → phải tra cứu thêm tài liệu và thử lại nhiều lần mới nắm được luồng hoạt động.

- **Hướng cải thiện:**
  - Tiếp tục luyện lab nhiều hơn để quen thuộc với CLI & Networking.
  - Làm thêm ví dụ thực tế về Spot Instance và Cost Optimization để hiểu sâu về quản lý chi phí.
  - Học song song với tài liệu chính thức AWS Docs để giảm nhầm lẫn giữa các dịch vụ tương tự.
  - Sau mỗi lab nâng cao, nên viết lại sơ đồ/tóm tắt luồng hoạt động để dễ ghi nhớ.


