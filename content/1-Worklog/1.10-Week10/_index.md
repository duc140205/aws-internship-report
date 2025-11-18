---
title: "Week 10 Worklog"
date: "2025-09-09"
weight: 2
chapter: false
pre: " <b> 1.10. </b> "
---
### Week 10 Objectives:

* Complete the initialization and deployment steps for the chatbot infrastructure.
* Integrate necessary AWS services for the system (CDK, Lambda, DynamoDB, Cognito, CloudFront, etc.).

### Tasks to be carried out this week:
| Day | Task | Start date | Completion date | Resources |
| --- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------ | --------------- | ----------------------------------------- |
| 2 | - Deploy messenger webhook on Meta Developers <br> - Start phase 1 of chatbot deployment using CDK | 10/11/2025 | 10/11/2025 | |
| 3 | - Test deploying local DB to sample chatbot on GitHub <br> - Test Vietnamese prompts and bot responses <br> - Some prompts OK, some time out (investigating cause) | 11/11/2025 | 11/11/2025 | |
| 4 | - Revise architecture, connect admin Lambda directly to DynamoDB in RAG <br> - Implement initial infrastructure and admin code | 12/11/2025 | 12/11/2025 | |
| 5 | - Finalize frontend hosting on S3 via CloudFront + Route 53 <br> - Set up Cognito for Admin | 13/11/2025 | 13/11/2025 | |
| 6 | - Research automating frontend deployment with CDK (S3 upload module) <br> - Modify VPC stack <br> - Explore Amplify JS vs AWS Amplify service <br> - Issue with Glue Catalog & Lambda in VPC <br> - Add Lambda outside VPC to invoke Glue Catalog/Crawler via API Gateway | 14/11/2025 | 14/11/2025 | |


### Week 10 Achievements:


* Started phase 1 of the chatbot using CDK.
* Tested deploying local DB to the sample chatbot and evaluated bot behavior with Vietnamese prompts.
* Analyzed timeout issues and hypothesized cause as bot misinterpreting the DB.
* Revised architecture and added direct connection from admin Lambda to DynamoDB.
* Completed the frontend via S3 + CloudFront + Route 53 and configured Cognito.
* Researched automating frontend deployment with CDK.
* Adjusted the VPC stack and clarified how Amplify JS differs from the AWS Amplify service.
* Solved the Glue Catalog issue by adding a Lambda outside the VPC to invoke it via API Gateway.
* Added a Lambda to trigger Glue Crawler when a user sends a request.