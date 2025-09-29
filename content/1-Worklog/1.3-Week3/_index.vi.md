---
title: "Worklog Tuần 3"
date: "2025-09-09"
weight: 1
chapter: false
pre: " <b> 1.3. </b> "
---



### Mục tiêu tuần 3:

* Nắm được kiến thức cơ bản và thực hành với các dịch vụ **lưu trữ** trên AWS:  
  - Amazon S3, Storage Gateway, AWS Backup, Amazon FSx.  
* Hiểu và áp dụng được các khái niệm về **bảo mật và phân quyền** trong AWS với IAM (User, Group, Role, Policy).  
* Rèn luyện kỹ năng sử dụng **AWS Console và CLI** để thao tác với dịch vụ.  
* Ghi chú, hệ thống hóa kiến thức để phục vụ cho các tuần sau.

### Các công việc cần triển khai trong tuần này:
| Thứ | Công việc                                                                                                                                                                                   | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu                            |
| --- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------ | --------------- | ----------------------------------------- |
| 2   | - Học & thực hành về Amazon S3, Snow Family, Storage Gateway, AWS Backup, Disaster Recovery                                        | 22/09/2025   | 22/09/2025      | [YouTube Playlist](https://www.youtube.com/watch?v=AQlsd0nWdZk&list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i), [Cloud Journey](https://cloudjourney.awsstudygroup.com/) |
| 3   | - Ghi chú & triển khai Amazon S3, AWS Backup                            | 23/09/2025   | 23/09/2025     | [Notion - Deploy AWS Backup](https://www.notion.so/Deploy-AWS-Backup-to-the-System-277d1c243c6a8059b6e6ec4f32511a00), [Notion - Amazon S3](https://www.notion.so/Kh-i-u-V-i-Amazon-S3-277d1c243c6a80e1a7b9fa625b0383bd) |
| 4   | - Thực hành triển khai File Storage Gateway | 24/09/2025  | 24/09/2025     | [Notion - File Storage Gateway](https://www.notion.so/Tri-n-khai-File-Storage-Gateway-278d1c243c6a8029bcbee7c8316d1b99) |
| 5   | - Thực hành triển khai FSx trên Windows                  | 25/09/2025   | 25/09/2025      | [Notion - FSx Windows](https://www.notion.so/Tri-n-khai-FSx-tr-n-Windows-279d1c243c6a80b8ba17ccb74f3a407a) |
| 6   | - Học & ghi chú dịch vụ Security trên AWS (IAM, Root Account, Role, Policy)                                                                                         | 26/09/2025   | 26/09/2025      | [YouTube Security](https://www.youtube.com/watch?v=N_vlJGAqZxo&list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i&index=151) |


### Kết quả đạt được tuần 3:

### Amazon S3
- Lưu trữ đối tượng, không giới hạn tổng dung lượng, mỗi object ≤ 5TB.  
- Tích hợp **event trigger**, hỗ trợ **multipart upload**.  
- Đảm bảo **durability 99.999999999%** và **availability 99.99%**.  
- **Storage Classes**: Standard, Standard-IA, Intelligent Tiering, One Zone-IA, Glacier/Deep Archive.  
- **Lifecycle Policy**: tự động di chuyển object giữa các lớp lưu trữ.  
- **Hosting static website**, hỗ trợ **CORS**.  
- **Kiểm soát truy cập**: ACL, Bucket Policy, IAM Policy.  
- **S3 Endpoint** cho truy cập qua mạng riêng, hỗ trợ **Versioning** để khôi phục khi xóa/ghi đè.  
- **Hiệu suất**: dùng **random prefix** để phân tán partition.  
- **Glacier**: lưu trữ chi phí thấp, 3 chế độ retrieve (Expedited, Standard, Bulk).

### Snow Family & Storage Gateway
- **Snowball**: 80TB, di chuyển dữ liệu on-premise → AWS.  
- **Snowball Edge**: 100TB + có tài nguyên compute để xử lý tại chỗ.  
- **Snowmobile**: xe container 100PB, phục vụ di chuyển exabyte dữ liệu.  
- **Storage Gateway**: giải pháp hybrid gồm 3 loại:  
  - **File Gateway (NFS/SMB)**: truy cập S3 như ổ đĩa mạng.  
  - **Volume Gateway (iSCSI)**: block storage, snapshot EBS.  
  - **Tape Gateway (VTL)**: thay thế hệ thống băng từ vật lý, lưu trữ trên S3/Glacier.  

### Backup & Disaster Recovery
- **RTO (Recovery Time Objective):** thời gian tối đa để phục hồi dịch vụ.  
- **RPO (Recovery Point Objective):** khoảng dữ liệu tối đa có thể mất.  
- Chiến lược DR: Backup & Restore, Pilot Light, Low Capacity Active-Active, Full Capacity Active-Active.  
- **AWS Backup**: dịch vụ tập trung để lên lịch, quản lý, theo dõi backup cho EBS, EC2, RDS, DynamoDB, EFS, Storage Gateway.

### FSx
- Thực hành triển khai **Amazon FSx for Windows File Server**.  
- Cung cấp lưu trữ file system native cho Windows, hỗ trợ SMB.  
- Phù hợp workload cần tích hợp AD và Windows-based app.

### Security & IAM
- **Shared Responsibility Model**: AWS quản lý hạ tầng, KH quản lý cấu hình & bảo mật ứng dụng.  
- **Root Account**: có toàn quyền, best practice → tạo IAM Admin, khóa thông tin root, chia quyền giữ credential, đảm bảo domain/email root.  
- **IAM User**: user trong 1 AWS Account, mặc định không có quyền, cần gán IAM Policy. Có thể nhóm thành IAM Group.  
- **IAM Policy**: viết dạng JSON, có 2 loại:  
  - Identity-based policy.  
  - Resource-based policy.  
  - Quy tắc: explicit deny luôn ưu tiên hơn allow.  
- **IAM Role**:  
  - Không có credentials riêng, phải **assume role** để nhận temporary credentials từ **STS**.  
  - Gồm **Policy** (quyền truy cập) & **Trust Policy** (ai được assume).  
  - Dùng để cấp quyền tối thiểu, cross-account access, hoặc cho EC2/Service.
