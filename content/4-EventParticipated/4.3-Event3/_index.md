---
title: "Event 3"
date: "2025-09-09"
weight: 1
chapter: false
pre: " <b> 4.3. </b> "
---

# Summary Report: “AWS Cloud Mastery Series #3: AWS Well-Architected – Security Pillar Workshop”

### Event Objectives
The workshop centered around the Security Pillar of the AWS Well-Architected Framework, giving participants a structured walk-through of five essential security domains:

- Pillar 1: Identity & Access Management (IAM)
- Pillar 2: Detection & Continuous Monitoring
- Pillar 3: Infrastructure Protection
- Pillar 4: Data Protection
- Pillar 5: Incident Response
  
It also included an introduction to AWS Cloud Clubs and the community-led activities supporting cloud learners across universities.

### Speakers

- **Le Vu Xuan An** - AWS Cloud Club Captain HCMUTE
- **Tran Duc Anh** - AWS Cloud Club Captain SGU
- **Tran Doan Cong Ly** - AWS Cloud Club Captain PTIT
- **Danh Hoang Hieu Nghi** - AWS Cloud Club Captain HUFLIT

- **Huynh Hoang Long** - AWS Community Builders
- **Dinh Le Hoang Anh** - AWS Community Builders

- **Nguyen Tuan Thinh** - Cloud Engineer Trainee
- **Nguyen Do Thanh Dat** - Cloud Engineer Trainee

- **Van Hoang Kha** - Cloud Security Engineer, AWS Community Builder

- **Thinh Lam** - FCJ Member
- **Viet Nguyen** - FCJ Member

- **Mendel Grabski (Long)** - Ex-Head of Security & DevOps, Cloud Security Solution Architect
- **Tinh Truong** - Platform Engineer at TymeX, AWS Community Builder 

### Key Highlights

#### AWS Cloud Club Introduction
The event opened with a brief introduction to the AWS Cloud Club initiative:
- A platform to develop cloud computing skills in real-world scenarios

- Opportunities for mentorship from AWS professionals

- Community building and collaboration across student groups

- Supported by multiple clubs including HCMUTE, SGU, PTIT, and HUFLIT

The main message: Cloud Clubs help students grow technically, professionally, and socially.


#### Identity & Access Management (IAM)
IAM was one of the most heavily emphasized parts of the workshop. Key takeaways:
- Enforce Least Privilege Access

- Remove root access keys after initial setup

- Avoid wildcard permissions (*)

- Use AWS SSO for centralized permission management in multi-account setups

- Understand SCPs (Organization-level permission guardrails)

- Apply Permission Boundaries to limit user/role privileges

Multi-factor authentication (MFA) methods—TOTP and FIDO2—were compared, highlighting trade-offs between usability, recovery, and security.

Secrets Manager’s automated credential rotation pipeline (create → set → test → finalize) was also explained as a best practice for handling sensitive credentials.


#### Detection & Continuous Monitoring
This segment detailed how AWS builds multi-layer visibility across an organization:
- Management Events (API calls, configuration changes)

- Data Events (object-level actions in S3 and Lambda execution logs)

- Network Events (VPC Flow Logs)

- Organization-wide coverage for consistent auditability

EventBridge’s role in alerting and automation was covered extensively—especially its ability to route events between accounts to create a centralized security workflow.

The "Detection-as-Code" concept was demonstrated using CloudTrail Lake and IaC deployments for automated, version-controlled detection logic.


#### Amazon GuardDuty
GuardDuty was highlighted as a fully managed threat-detection service that analyzes CloudTrail events, VPC Flow Logs, and DNS queries to spot risks such as disabled logging, unusual network traffic, or malicious domain lookups.

The session also covered advanced protections like S3 malware scanning, EKS audit log monitoring, RDS anomaly detection, Lambda network analysis, and runtime protection via the GuardDuty Agent.

Finally, the speakers connected GuardDuty’s features to major frameworks like AWS Foundational Security Best Practices and the CIS Benchmarks.


#### Network Security Controls
Key infrastructure protection topics included:

- Threat categories: Ingress, Egress, and Insider attacks

- Differences between Security Groups (stateful) and NACLs (stateless)

- Route 53 Resolver for DNS routing and hybrid environments

- AWS Network Firewall use cases: egress filtering, segmentation, IDS/IPS

- Integration with GuardDuty threat intel for automated blocking


#### Data Protection & Governance
The session reinforced why encryption and proper credential handling are mandatory in AWS:
- KMS key hierarchy (CMK → Data Key)

- Using IAM conditions to limit cryptographic operations

- ACM for certificate automation and DNS-based validation

- Secrets Manager rotation patterns

- Enforcing TLS connections in S3 and DynamoDB

- RDS SSL/TLS configuration and server identity verification

#### Incident Response & Prevention
Prevention Best Practices: Emphasis was placed on using temporary credentials, avoiding direct exposure of S3 buckets, isolating critical components in private subnets, enforcing Infrastructure as Code for consistency, and requiring two layers of approval for high-risk changes (code review plus pipeline deployment).

Incident Response Process: The workshop outlined a five-stage workflow: preparing in advance, detecting and analyzing issues, containing the threat by isolating resources or revoking access, restoring systems during eradication and recovery, and finally documenting lessons learned afterward.


### Applying to Work
The workshop’s key security concepts apply directly to our AI Chatbot project. Strengthening IAM practices helps us define safer, more controlled access for our backend services and admin tools. The focus on logging, monitoring, and infrastructure protection gives us a clearer plan for how to track system activity and prevent misconfiguration. The incident response framework also helps our team react faster and more systematically whenever issues arise. Overall, these takeaways help us build a more secure and reliable chatbot platform.

### Event Experience
- The event was well-organized and engaging, with knowledgeable speakers who communicated complex security topics clearly.
- Interactive Q&A sessions allowed participants to clarify doubts and deepen their understanding.

#### Some event photos
![Event Photo 1](/images/4-EventParticipated/4.3-Event3/1.jpg)
![Event Photo 2](/images/4-EventParticipated/4.3-Event3/2.jpg)
![Event Photo 3](/images/4-EventParticipated/4.3-Event3/3.jpg)