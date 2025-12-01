---
title: "Week 4 Worklog"
date: "2025-09-09"
weight: 1
chapter: false
pre: " <b> 1.4. </b> "
---
### Week 4 Objectives:

* Deepen understanding of Identity & Security in AWS:
  * Learn how access management services work: **IAM**, **Cognito**, **AWS Identity Center (SSO)**, and **Organizations**.
  * Understand data encryption using **AWS KMS** and apply **encrypt at rest** in practice.

* Get familiar with and practice **AWS Security Hub** to aggregate and assess system security standards.

* Understand **IAM Role, Condition keys, and Permission Boundaries**, and apply them to limit and control resource access.

* Learn how to analyze and optimize cost between EC2 and Lambda to choose the right service per scenario.

* Practice reading and translating AWS technical documentation to support in-depth knowledge synthesis and internal sharing.


### Tasks to carry out this week:
| Day | Tasks                                                                                                                                                                                   | Start date | Completion date | Reference Material                            |
| --- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------- | --------------- | ------------------------------------- |
| 2   | - Study services related to **Identity & Security** in AWS: <br> &emsp; + **Amazon Cognito:** Authentication, authorization, and user management for web & mobile apps.<br> &emsp;&emsp;• Learn **User Pools** (user signup/sign-in) and **Identity Pools** (granting access to other AWS services).<br><br> &emsp; + **AWS Organizations:** Central management of multiple AWS Accounts, use **OUs**, **Consolidated Billing**, and **Service Control Policies (SCPs)**.<br><br> &emsp; + **AWS Identity Center (SSO):** Manage access to AWS Accounts & external applications; learn **Identity source** and **Permission Sets**.<br><br> &emsp; + **AWS KMS:** Key management; learn **CMK**, **Data Key**, and **encrypt at rest** mechanism.<br><br> - Practice labs: <br> &emsp; + Lab 2: IAM Role ✅ <br> &emsp; + Lab 30: IAM Permission Boundary ✅ <br> &emsp; + Lab 27: Tag and Resource Groups ✅ <br> &emsp; + Lab 28: Manage EC2 via Resource Tags <br> &emsp; + Lab 18: AWS Security Hub ✅ <br> &emsp; + Lab 12: AWS SSO (SUS) <br> &emsp; + Lab 33: KMS Workshop ✅ <br> &emsp; + Lab 44: IAM Role and Condition <br> &emsp; + Lab 48: IAM Role and Application <br> &emsp; + Lab 22 ✅ | 29/09/2025 | 29/09/2025      | [AWS Study Group YouTube Playlist](https://www.youtube.com/watch?v=pZ2fgEFK3Vs&list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i&index=152) |
| 3   | - **Study & practice AWS Security Hub:** <br> &emsp; + Enable Security Hub and integrate with other security services (GuardDuty, Config, Inspector). <br> &emsp; + Check and evaluate security standards (CIS AWS Foundations Benchmark, PCI DSS, etc.). <br> &emsp; + Analyze Findings and handle security alerts. <br><br> - **Cost comparison & optimization between EC2 and AWS Lambda:** <br> &emsp; + Analyze pricing models: EC2 (runtime-based) vs Lambda (requests & execution duration). <br> &emsp; + Evaluate suitable use cases and select the more cost-effective service. <br><br> - **Manage EC2 access using Resource Tags and AWS IAM:** <br> &emsp; + Create tag-based IAM policies. <br> &emsp; + Restrict EC2 resource access by Tag. <br> &emsp; + Test and verify access controls. | 30/09/2025 | 30/09/2025      | [Get started with AWS Security Hub](https://www.notion.so/Get-started-with-AWS-Security-Hub-27ed1c243c6a80b98608e1ac3a8fbecd?pvs=21) <br> [EC2 vs Lambda cost optimization](https://www.notion.so/T-i-u-chi-ph-EC2-v-i-Lambda-27ed1c243c6a80859243ca434584246e?pvs=21) <br> [Manage EC2 access via Resource Tags](https://www.notion.so/Qu-n-l-truy-c-p-v-o-d-ch-v-EC2-Resource-Tag-v-i-AWS-IAM-27ed1c243c6a80b1abeff843655d0676?pvs=21) |
| 4   | - **Study IAM Role and Condition in AWS IAM:** <br> &emsp; + Review IAM Roles and how to attach Roles to AWS services (EC2, Lambda...). <br> &emsp; + Differentiate **Trust Policies** and **Permission Policies**. <br> &emsp; + Explore **Condition keys** in IAM Policies to restrict access by conditions (e.g., `aws:SourceIp`, `aws:RequestedRegion`, or by **Tag**). <br> &emsp; + Lab: configure and test IAM Role with specific conditions. <br><br> - **Study “Encrypt at rest” with AWS KMS:** <br> &emsp; + Review **CMK (Customer Managed Key)** and **Data Key** concepts. <br> &emsp; + Practice encrypting stored data using AWS KMS on S3/EC2. <br> &emsp; + Distinguish **encryption at rest** vs **encryption in transit**. | 01/10/2025 | 01/10/2025      | [IAM Role Condition](https://www.notion.so/IAM-Role-Condition-280d1c243c6a80479047cffc35a67c50?pvs=21) <br> [Encrypt at rest with AWS KMS](https://www.notion.so/Encrypt-at-rest-with-AWS-KMS-27ed1c243c6a8018b6ccce2b7de75729?pvs=21) |
| 5   | - **Limit User permissions with IAM Permission Boundaries:** <br> &emsp; + Review **IAM Policy** and **Role-based Access Control (RBAC)**. <br> &emsp; + Learn how Permission Boundaries act as a **maximum limit** for IAM User or Role permissions. <br> &emsp; + Differentiate between regular IAM Policies and Permission Boundary Policies. <br> &emsp; + Lab: create a User and attach a Permission Boundary to limit actions (e.g., allow creating EC2 only in a specific region). <br> &emsp; + Verify results via AWS CLI and Console. | 02/10/2025 | 02/10/2025      | [Limit user permissions with IAM Permission Boundary](https://www.notion.so/GI-I-H-N-QUY-N-C-A-USER-V-I-IAM-PERMISSION-BOUNDARY-27ed1c243c6a801c9b71cb52135090fc?pvs=21) |
| 6   | - Translate blog & materials related to AWS / Cloud: <br> &emsp; + Translate Document 1: "AWS recognized as Leader in 2024-25 Omdia Universe for Cloud Container Management & Services" <br> &emsp; + Translate Document 2: "AWS Savings Plans: How to Implement an Effective Chargeback Strategy" <br> &emsp; + Translate Document 3: "AWS Weekly Roundup: Amazon S3 Express One Zone price cuts, Pixtral Large on Amazon Bedrock, Amazon Nova Sonic, and more (April 14, 2025)" | 03/10/2025 | 03/10/2025      | [Google Doc 1](https://docs.google.com/document/d/1tIYmhfVruIrpmRvHdUgwRzxpMvA1cdvpShytAxsNreQ/edit?tab=t.0) <br> [Google Doc 2](https://docs.google.com/document/d/1w7ObsIEvyJNPV3RWgjmvAxLa3lZz3s3kpSJWGpyYV7U/edit?usp=sharing) <br> [Google Doc 3](https://docs.google.com/document/d/1l9fOfRkPtOaiZ2pZh3qPM5xkh1UxKkL0G3ihQA6S0LM/edit?usp=sharing) |


### Week 4 Achievements:

* Completed study and hands-on practice of **Identity & Security** related services in AWS, including:
  * **Amazon Cognito** – authentication and user authorization for web/mobile apps.
  * **AWS Organizations** – central management of multiple accounts with OUs, SCPs, and Consolidated Billing.
  * **AWS Identity Center (SSO)** – managing access to multiple AWS accounts and external apps.
  * **AWS KMS (Key Management Service)** – key management and encrypt-at-rest practices.
  * **AWS Security Hub** – monitoring & assessing overall security posture.
  * **IAM Permission Boundary** – setting maximum permission limits for users/roles.

* Completed security & access management labs:
  * IAM Role & Condition ✅  
  * Permission Boundary ✅  
  * Security Hub ✅  
  * Tag-based Access Control for EC2 ✅  
  * Encrypt at rest with AWS KMS ✅  

* Mastered IAM policy concepts and their application:
  * **Trust Policy**, **Permission Policy**, and **Condition Keys**.  
  * Applied tag-based policies to restrict resource access based on practical conditions.

* Learned how to **assess & optimize costs** between EC2 and Lambda to choose the appropriate service per workload.

* Translated and summarized **3 in-depth AWS & Cloud documents/blogs**:
  * [Document 1 – AWS recognized as Leader in 2024-25 Omdia Universe](https://docs.google.com/document/d/1tIYmhfVrulrpmRvHdUgwRzxpMvA1cdvpShytAxsNreQ/edit?usp=sharing)  
  * [Document 2 – AWS Savings Plans: Chargeback Strategy](https://docs.google.com/document/d/1w7ObsIEvyJNPV3RWgjmvAxLa3LZz3s3kpSJWGpyYV7U/edit?usp=sharing)  
  * [Document 3 – AWS Weekly Roundup (April 14, 2025)](https://docs.google.com/document/d/1l9fOfRkPtOaiZ2pZh3qPM5xkh1UxKkL0G3ihQA6S0LM/edit?usp=sharing)

* Improved ability to **read – translate – analyze** English technical AWS documentation, strengthening foundational Cloud Security knowledge.