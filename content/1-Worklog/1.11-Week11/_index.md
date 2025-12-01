---
title: "Week 11 Worklog"
date: "2025-09-09"
weight: 2
chapter: false
pre: " <b> 1.11. </b> "
---

### Week 11 Objectives:

* Complete and stabilize the **data analytics pipeline** by migrating from Glue Crawler to Athena DDL to reduce cost and simplify the architecture.
* Standardize the **Lambda system**, separating responsibilities between AdminManager and Analytics Lambda, while ensuring stability when querying Athena and interacting with RDS.
* Clarify the operation of **Amazon Cognito**, especially the user pool mechanism and its independence from the database, in preparation for authentication integration.
* Implement and finalize the **admin frontend**, mock data, and connect to the backend to visualize the real data flow from S3 → Athena → Dashboard.
* Ensure the underlying infrastructure operates correctly by successfully deploying the **login page** via CloudFront and testing the CDK/CloudFormation workflow.

### Tasks to be carried out this week:
| Day | Task | Start Date | Completion Date | Reference Material |
| --- | ----- | ----------- | ---------------- | ------------------ |
| 2   | **Kickoff of the work week**: Deploy infrastructure, create Glue resources, and run GlueHandler outside the VPC to crawl data. Update frontend and mock data to visualize the data flow from S3 → Glue/Athena → Admin Dashboard. Cognito integration is postponed to prioritize the data pipeline. | 17/11/2025 | 17/11/2025 | |
| 3   | **Analytics redesign**: Decide to remove Glue to reduce complexity, switching to Lambda + Athena DDL to define schemas and query data manually. Conduct team meeting and demo UI to finalize data visualization. Deep dive into Cognito. | 18/11/2025 | 18/11/2025 | |
| 4   | **Cleanup & architectural restructuring**: Delete Glue database, Athena endpoint; update AdminManager Lambda to only insert data into RDS. Create a new Analytics Lambda running outside the VPC to process Athena queries. Update admin_stack, handle missing user pool issue, remove Glue crawler, and explore Athena DDL vs Glue. | 19/11/2025 | 19/11/2025 | |
| 5   | **Detailing Athena DDL & Cognito**: Study deeper into manually defining schema using DDL — flexible, free, real-time. Clarify that Cognito operates independently and does not depend on the database. Write Jira notes regarding testing domain deployment using CDK. | 20/11/2025 | 20/11/2025 | |
| 6   | **Deploy Frontend Dashboard with Cognito**: Team meeting and successfully deploy the login page via CloudFront (Route 53 not used yet). Finalize logic of `admin_handler` to allow admin to insert data into RDS via the frontend. | 21/11/2025 | 21/11/2025 | |

### Week 11 Achievements:

* Deployed initial infrastructure and tested Glue + Lambda catalog.
* Changed analytics direction, fully migrating to Athena DDL.
* Removed Glue DB, crawler, and endpoint; optimized overall architecture.
* Created a new Analytics Lambda to query Athena outside the VPC.
* Gained clear understanding of Cognito’s independence from the database.
* Successfully deployed the login page on CloudFront.
* Completed admin_handler logic to allow inserting data into RDS.
