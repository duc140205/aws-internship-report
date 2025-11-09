---
title: "Proposal"
date: "2025-09-09"
weight: 2
chapter: false
pre: " <b> 2. </b> "
---

# AI-Powered Booking Chatbot on AWS
## AWS Serverless RAG-integrated solution for booking and customer care

### 1. Executive Summary  
The AI-Powered Booking Chatbot on AWS is an intelligent chatbot solution designed to help users book appointments and look up service information via Facebook Messenger. The system combines Retrieval-Augmented Generation (RAG) with a SQL-driven model to handle natural conversations while retrieving accurate data from a PostgreSQL database. The platform uses an AWS Serverless architecture to reduce operational costs, scale automatically, and provide high reliability.

### 2. Problem Statement  
Current problem  
Traditional booking systems often require manual or web-based interactions, lack natural conversational capabilities and contextual responses. Deploying AI chatbots can be complex without a flexible cloud platform to manage data, intents, and security.

Solution  
The project uses AWS Lambda, API Gateway, DynamoDB, PostgreSQL, and AI-supporting services to build a versatile chatbot capable of:
  - Conversational intent analysis (booking, consultation, general questions).
  - Connecting to databases to retrieve schedules, customer information, or analytical data.
  - Supporting a RAG module for open-ended questions or complex contexts.
  - Providing an Admin Dashboard to monitor conversation history, statistics, and system performance.

Benefits and ROI  
The solution reduces operational costs (vs. on-premises), and creates a practical learning environment for students/research teams on AWS Serverless, NLP, and RAG. The system is reusable and extendable for SMBs in the future.

### 3. Solution Architecture  
Overview:  
The platform runs Serverless + VPC-secured, with all conversation processing, scheduling, and AI data handled by AWS Lambda and other serverless services.

![Chatbot Architecture](/images/2-Proposal/chatbot_final_final.drawio.png)

Main data flow
1. User chats via Facebook Messenger → API Gateway → Lambda WebhookReceiver.
2. Lambda ChatOrchestrator handles intent and calls the Intent Model or RAG Module.
3. DynamoDB stores conversation cache and metadata, while PostgreSQL stores booking records and history.
4. EventBridge manages jobs to archive database records to S3 (e.g., daily archive) for the Admin Dashboard.
5. Admin Dashboard (Route 53 + CloudFront + S3 + Cognito) allows admins to monitor, test, and manage the system.

AWS services used
- AWS Lambda: conversation processing, intent orchestration, scheduling.
- Amazon API Gateway: connects Messenger and the Admin Dashboard.
- Amazon DynamoDB: cache, logs, and RAG metadata.
- Amazon RDS (PostgreSQL): booking records and interaction history.
- Amazon EventBridge: event management and cron jobs.
- Amazon S3 + CloudFront + Route 53: hosting and distribution for the Admin UI.
- Amazon Cognito: user management and admin authorization.
- AWS Secrets Manager: secure storage for service credentials.
- AWS Glue + Athena (optional analytics): extract and analyze conversation history data.

### 4. Technical Deployment  
Deployment stages  
The project has two parts — the chatbot system and the AI Booking admin platform — each with four stages:

1. Research and architecture design  
   - Analyze chatbot models integrating RAG and intent classification.  
   - Propose an AWS Serverless architecture: Lambda, API Gateway, RDS PostgreSQL, DynamoDB, EventBridge.  
   - Research CI/CD using AWS CDK or CloudFormation for automated deployments.  
   - (Pre-workshop: prepare technical environment and architecture diagrams.)

2. Cost estimation and feasibility checks  
   - Use AWS Pricing Calculator to estimate infrastructure costs (Lambda, RDS, DynamoDB, Amplify, Cognito, EventBridge, S3, CloudFront).  
   - Run small sandbox tests to validate scalability, response times, and stability.  
   - (Early workshop: use results to tune resources and sizing.)

3. Architecture refinement and optimization  
   - Balance cost and performance: optimize Lambda counts, reduce RDS cost using caching with DynamoDB.  
   - Implement conversation flow separation between "Booking" and "Customer Service" intents to reduce processing overhead.  
   - Test scalability under concurrent users.  
   - (Mid-workshop: ensure cost-effective and technically optimal system.)

4. Development, testing and deployment  
   - Develop core Lambdas: WebhookReceiver, ChatOrchestrator, RAG Module; integrate RDS and DynamoDB.  
   - Configure API Gateway, EventBridge, and Cognito; build the Admin UI with JavaScript.  
   - End-to-end testing: Messenger → API Gateway → Chatbot → Database → Dashboard.  
   - (End of workshop: put system into operation, record results and deliver final demo.)

Technical requirements  
- Core platform: AWS Serverless (Lambda, API Gateway, DynamoDB, RDS PostgreSQL, EventBridge).  
- Security: Amazon Cognito, AWS Secrets Manager, segregated IAM Roles.  
- Development: AWS CDK/SDK, JavaScript for the Admin UI.  
- External integration: Facebook Messenger Webhook (API Gateway endpoint).  
- Automation: CloudFormation templates.

### 5. Roadmap & Milestones  
- Internship period (Sep–Dec):  
  - Sep: Learn AWS, solidify serverless architecture, build prototype.  
  - Oct: Design and refine architecture.  
  - Nov: Develop and test the system.  
  - Dec: Deploy fully, demo and evaluate results.  
- Post-deployment: further research and improvements over 12 months.

### 6. Budget Estimate  
- Download the budget estimate report (PDF): [Budget Estimate - PDF](/images/2-Proposal/chatbotestimation.pdf)

### 7. Risk Assessment

| Risk | Impact | Probability | Mitigation |
|---|---:|---:|---|
| Messenger webhook outage | Medium | Medium | Implement retries & log monitoring via CloudWatch. |
| Incorrect Lambda permissions | High | Low | Use dedicated IAM roles and perform least-privilege permission tests. |
| DynamoDB data congestion | Medium | Low | Apply TTL limits and local caching. |
| Cost overrun | Medium | Medium | Monitor AWS Billing Alerts and enable Budget notifications. |

### 8. Expected Outcomes  
- Technical: Deliver a working AI chatbot capable of booking via Messenger and responding to customer queries automatically.  
- Academic: Workshop participants gain an understanding of designing AWS Serverless architectures integrated with RAG.  
- Practical: Scale the model into an enterprise chatbot and combine conversation analytics with Glue & Athena.  
- Long-term value: Lay the foundation for an internal Customer Service AI platform or a SaaS product.