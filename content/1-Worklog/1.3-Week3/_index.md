---
title: "Week 3 Worklog"
date: "2025-09-09"
weight: 1
chapter: false
pre: " <b> 1.3. </b> "
---
### Week 3 Objectives:

* Learn and practice AWS storage services:  
  - Amazon S3, Storage Gateway, AWS Backup, Amazon FSx.  
* Understand and apply AWS security and authorization concepts with IAM (User, Group, Role, Policy).  
* Practice using the AWS Console and CLI to operate services.  
* Take notes and organize knowledge to support following weeks.

### Tasks to carry out this week:
| Day | Tasks                                                                                                                                                                                   | Start date  | Completion date | References                            |
| --- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------- | --------------- | ------------------------------------- |
| 2   | - Learn & practice Amazon S3, Snow Family, Storage Gateway, AWS Backup, Disaster Recovery                                        | 22/09/2025  | 22/09/2025      | [YouTube Playlist](https://www.youtube.com/watch?v=AQlsd0nWdZk&list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i), [Cloud Journey](https://cloudjourney.awsstudygroup.com/) |
| 3   | - Note & deploy Amazon S3, AWS Backup                                                                                         | 23/09/2025  | 23/09/2025      | [Notion - Deploy AWS Backup](https://www.notion.so/Deploy-AWS-Backup-to-the-System-277d1c243c6a8059b6e6ec4f32511a00), [Notion - Amazon S3](https://www.notion.so/Kh-i-u-V-i-Amazon-S3-277d1c243c6a80e1a7b9fa625b0383bd) |
| 4   | - Practice deploying File Storage Gateway                                                                                     | 24/09/2025  | 24/09/2025      | [Notion - File Storage Gateway](https://www.notion.so/Tri-n-khai-File-Storage-Gateway-278d1c243c6a8029bcbee7c8316d1b99) |
| 5   | - Practice deploying FSx on Windows                                                                                           | 25/09/2025  | 25/09/2025      | [Notion - FSx Windows](https://www.notion.so/Tri-n-khai-FSx-tr-n-Windows-279d1c243c6a80b8ba17ccb74f3a407a) |
| 6   | - Study & document AWS Security services (IAM, Root Account, Role, Policy)                                                     | 26/09/2025  | 26/09/2025      | [YouTube Security](https://www.youtube.com/watch?v=N_vlJGAqZxo&list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i&index=151) |


### Week 3 Achievements:

### Amazon S3
- Object storage with virtually unlimited total capacity; each object ≤ 5 TB.  
- Supports event triggers and multipart upload.  
- Durability 99.999999999% and availability 99.99%.  
- Storage classes: Standard, Standard-IA, Intelligent-Tiering, One Zone-IA, Glacier/Deep Archive.  
- Lifecycle policies to transition objects between storage classes automatically.  
- Static website hosting and CORS support.  
- Access control: ACLs, Bucket Policy, IAM Policy.  
- S3 Endpoints for private network access; Versioning for recoverability from deletion/overwrite.  
- Performance: use random prefixes to distribute partitions.  
- Glacier: low-cost archival with three retrieval options (Expedited, Standard, Bulk).

### Snow Family & Storage Gateway
- Snowball: ~80 TB appliance for on-prem → AWS data transfer.  
- Snowball Edge: ~100 TB + on-device compute for local processing.  
- Snowmobile: container truck for up to ~100 PB for exabyte-scale transfers.  
- Storage Gateway (hybrid) types:  
  - File Gateway (NFS/SMB): access S3 as a file share.  
  - Volume Gateway (iSCSI): block storage with snapshots to EBS/S3.  
  - Tape Gateway (VTL): replace physical tape infrastructure, store to S3/Glacier.

### Backup & Disaster Recovery
- RTO (Recovery Time Objective): max time to restore service.  
- RPO (Recovery Point Objective): maximum acceptable data loss window.  
- DR strategies: Backup & Restore, Pilot Light, Low-capacity Active-Active, Full-capacity Active-Active.  
- AWS Backup: centralized service to schedule, manage, and monitor backups for EBS, EC2, RDS, DynamoDB, EFS, Storage Gateway.

### FSx
- Practiced deploying Amazon FSx for Windows File Server.  
- Provides native Windows file system storage with SMB support.  
- Suited for workloads requiring AD integration and Windows-based applications.

### Security & IAM
- Shared Responsibility Model: AWS manages infrastructure; customers manage configuration and application security.  
- Root Account: full privileges — best practice: create an IAM admin, secure root credentials, restrict root use, ensure root email/domain control.  
- IAM User: account-scoped user, has no permissions by default and requires IAM policies; can be grouped via IAM Groups.  
- IAM Policy: JSON documents; two main types: identity-based and resource-based. Rule: explicit deny overrides allow.  
- IAM Role:  
  - No long-term credentials; must be assumed to obtain temporary credentials via STS.  
  - Consists of Policies (permissions) and a Trust Policy (who can assume).  
  - Used for least-privilege access, cross-account access, or granting permissions to EC2/services.