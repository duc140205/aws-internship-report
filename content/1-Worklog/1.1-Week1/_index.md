---
title: "Week 1 Worklog"
date: "2025-09-09"
weight: 1
chapter: false
pre: " <b> 1.1. </b> "
---



### Week 1 Objectives:

* Get to know members of the **First Cloud Journey (FCJ)** program and understand the rules and regulations at the internship unit.  
* Understand basic concepts of **cloud computing** and the AWS service ecosystem (Compute, Storage, Networking, Database, Security…).  
* Practice creating and managing an AWS Free Tier account following **best practices**: IAM User, Group, Role; minimize use of the root account; set up Budgets to monitor costs.  
* Use both **AWS Management Console** and **AWS CLI** for resource operations and get familiar with scripting for automation.  
* Learn cost optimization mechanisms: Spot Instances, AWS Pricing Calculator, Budgets/Cost Budgets.  
* Get familiar with **Serverless** concepts (Lambda, DynamoDB) and the **Hugo** tool to publish static workshop sites.  
* Understand and practice basic **AWS Networking**: VPC, Subnet, Route Table, Security Group, NACL, IGW, NAT GW, VPC Endpoint, VPC Flow Logs, VPN, Direct Connect, Elastic Load Balancing.

### Tasks to carry out this week:
| Day | Tasks                                                                                                                                                                                   | Start date  | Completion date | Reference Material                             |
| --- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------- | --------------- | ----------------------------------------- |
| 2   | - Meet FCJ members <br> - Read and note the internship rules and regulations <br> - Overview of cloud computing Module 01 - 01 → 07: basic AWS overview, AWS infrastructure, policies, services, management and cost optimization via Budgets, contact AWS support. <br>- **Hands-on:** <br>&emsp; + Create AWS Free Tier account <br>&emsp; + Install & configure AWS CLI <br>&emsp; + Create IAM User, Group, Role to manage the account instead of using root <br>&emsp; + Setup Budget/Cost Budget to monitor monthly credits <br> - Learn how to request AWS Support assistance   | 08/09/2025  | 08/09/2025      |   <https://000001.awsstudygroup.com/> <br>  <https://000007.awsstudygroup.com/> <br>  <https://000009.awsstudygroup.com/> |
| 3   | - Learn Hugo to build the AWS workshop site: install, project structure, run locally <br> - Complete Module 1 labs <br> - Study cost optimization with Spot Instances (~90% cost reduction, but resources can be reclaimed) <br> - Understand **Serverless** (no server management, e.g., Lambda, DynamoDB) <br> - Use AWS Pricing Calculator: estimate, share, compare by region <br> - Networking services: Amazon VPC, VPC Peering, Transit Gateway, VPN, Direct Connect, Elastic Load Balancing <br> - **Key concept:** VPC = virtual private network in a Region; divide subnets by AZ; control with Route Tables + Security (SG, NACL)                                            | 09/09/2025  | 09/09/2025      | <https://van-hoang-kha.github.io/> |
| 4   | - IAM Role lab: <br>&emsp; + Create & manage IAM Groups, Users, Roles <br>&emsp; + Attach managed & inline policies <br>&emsp; + Sign in as IAM User and switch Roles <br> - Learn VPC basics: public/private subnets, Route Tables, IGW, NAT GW <br> - ENI (Elastic Network Interface), EIP (Elastic IP) <br> - VPC Endpoints (Interface & Gateway) <br> - Security Group (stateful) vs NACL (stateless) <br> - VPC Flow Logs (CloudWatch / S3) <br> - VPC Peering & its limitations <br> - Transit Gateway & Attachments <br> - Complete Module 02 - 01 → 02 | 10/09/2025  | 10/09/2025      | <https://cloudjourney.awsstudygroup.com/> |
| 5   | - Site-to-Site VPN (Virtual Private Gateway & Customer Gateway) <br> - Client VPN basics <br> - AWS Direct Connect (Hosted/Dedicated) <br> - Elastic Load Balancing (ELB): ALB, NLB, CLB, Global LB <br>&emsp; + Health checks, sticky sessions, access logs <br>&emsp; + Path-based routing, target types <br> - Complete Module 02 - 03                  | 11/09/2025  | 11/09/2025      | <https://cloudjourney.awsstudygroup.com/> |
| 6   | - Review learned topics (VPC, Subnet, IAM, Security, ELB…) <br> - Advanced VPC lab practice <br> - Get familiar with Route 53 Resolver (Hybrid DNS) <br> - Practice VPC Peering                                                                                         | 12/09/2025  | 14/09/2025      | [Summary notes](https://www.notion.so/C-c-t-c-n-ghi-nh-26ad1c243c6a80159943e7d394e4ca40?pvs=21) <br> [AWS VPC](https://www.notion.so/M-i-tr-ng-AWS-VPC-26bd1c243c6a80ceab10c980d039587d?pvs=21) <br> [Route 53 Resolver](https://www.notion.so/Thi-t-l-p-Hybrid-DNS-v-i-Route-53-Resolver-26dd1c243c6a8001ad9cf56de336df6b?pvs=21) <br> [VPC Peering](https://www.notion.so/Thi-t-l-p-VPC-Peering-26ed1c243c6a8070af32e2113871d9a9?pvs=21) |


### Week 1 Achievements:

- **Fundamental AWS knowledge**
  - Understand what AWS is and the main service groups: Compute, Storage, Networking, Database, Security…
  - Distinguish between **AWS Management Console**, **AWS CLI**, and **AWS SDK**.

- **Hands-on with AWS Free Tier**
  - Successfully created and configured an AWS Free Tier account.
  - Installed and configured AWS CLI (Access Key, Secret Key, default Region).
  - Managed AWS resources via both **Console (Web)** and **CLI**.

- **AWS CLI skills**
  - Checked account info & CLI configuration.
  - Listed available Regions.
  - Worked with EC2: view instances, create/manage key pairs, check running services.
  - Learned to write basic scripts to automate tasks.

- **IAM (Identity and Access Management)**
  - Created & managed IAM Users, Groups, Roles.
  - Attached managed and inline policies.
  - Signed in as IAM User and practiced Role switching.
  - Understood importance of avoiding root account use.

- **AWS cost optimization**
  - Understood Spot Instance behavior (up to ~90% cost reduction, but can be reclaimed).
  - Created Budgets and Cost Budgets to track credits.
  - Used AWS Pricing Calculator to estimate and compare costs by region.

- **Serverless & Workshop**
  - Understood **Serverless** concepts: Lambda, DynamoDB, and other managed services.
  - Got familiar with **Hugo** for building static workshop sites on AWS.

- **AWS Networking**
  - Understood **VPC (Virtual Private Cloud)**: virtual private network in a Region.
  - Differentiated public/private subnets, Route Tables, IGW, NAT GW.
  - Learned about Elastic IP, ENI, VPC Endpoints, VPC Flow Logs.
  - Compared Security Groups (stateful) vs NACLs (stateless).
  - Learned about VPC Peering, Transit Gateway, and limitations.
  - Got an introduction to Site-to-Site VPN, Client VPN, and Direct Connect.
  - Understood types of Elastic Load Balancers (ALB, NLB, CLB, global LB).

---

✅ After week 1, foundations are in place for:
- Secure AWS account management (IAM, Budgets).
- Using CLI/Console for AWS operations.
- Basic Networking knowledge (VPC, Subnet, VPN, ELB).
- Understanding cost optimization techniques.
- Ready for advanced labs (Route 53, Peering, Hybrid DNS, …).


### Reflection – Self-assessment and challenges in week 1

- **Strengths achieved:**
  - Clear understanding of AWS basics and multiple ways to manage resources (Console, CLI, SDK).
  - Proficient in account setup and IAM best practices (avoiding root account).
  - Better system-level view of AWS service organization, especially Networking.

- **Challenges encountered:**
  - Initially confused between AWS CLI and SDK → clarified after hands-on practice.
  - VPC concepts (subnet, CIDR, NACL, Security Group) are complex and easy to mix up while learning theory and labs simultaneously.
  - Could not find `EC2:Running Hours` option when creating Budget Usage → likely due to lack of real account usage data.
  - Estimating costs in Pricing Calculator was initially difficult due to unfamiliarity with service types and region choices.
  - Advanced labs (VPC Peering, Route 53 Resolver, Hybrid DNS) were challenging on first exposure → required extra documentation and repeated attempts to understand workflows.

- **Improvement plan:**
  - Continue practicing labs to gain familiarity with CLI & Networking.
  - Add practical Spot Instance and cost optimization exercises to deepen cost management skills.
  - Study official AWS Docs in parallel to reduce confusion between similar services.
  - After each advanced lab, create diagrams/summaries of workflows to aid retention.
