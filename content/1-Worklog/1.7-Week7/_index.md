---
title: "Week 7 Worklog"
date: "2025-09-09"
weight: 1
chapter: false
pre: " <b> 1.7. </b> "
---
### Week 7 Objectives:

* Learn how to deploy and optimize AWS architecture for a real project.  
* Review core AWS fundamentals.  
* Experiment with deploying a Text-to-SQL chatbot and evaluate extension directions.  
* Analyze database security and data-processing logic in the system.



### Tasks to carry out this week:
| Day | Tasks | Start date | Completion date | Reference Material |
| --- | ----- | ---------- | --------------- | ----------- |
| 2 | - Study how to downscale the project. <br> - Learn how to implement an architecture on AWS. <br> - Note a rare incident: **AWS outage in us-east-1**, affecting many systems. | 20/10/2025 | 20/10/2025 | Internal AWS reports, incident reports |
| 3 | - Review core AWS knowledge to prepare for assessments. | 21/10/2025 | 21/10/2025 | <https://cloudjourney.awsstudygroup.com/> |
| 4 | - Redraw the overall architecture and **estimate pricing** for the project. <br> - Define the initial **direction for the project chatbot**. <br> - [Direction document (Notion)](https://www.notion.so/295d23b23efb80bb9500e5cb3222414c?pvs=21) | 22/10/2025 | 22/10/2025 | Internal Notion |
| 5 | - Study **database security and safe data logic** to prevent invalid user operations (incorrect update/insert/delete). <br> - **Deploy the Text2SQL chatbot** following the AWS Blog guide. <br> - [AWS Blog: Build an AI-powered Text-to-SQL Chatbot](https://aws.amazon.com/vi/blogs/database/build-an-ai-powered-text-to-sql-chatbot-using-amazon-bedrock-amazon-memorydb-and-amazon-rds/?utm_source=chatgpt.com) | 23/10/2025 | 23/10/2025 | AWS Blog |
| 6 | - Read and understand the **Text2SQL chatbot source code**. <br> - [Meeting notes on Notion](https://www.notion.so/NOTE-h-p-298d23b23efb8072a6a3e1f67d5c640a?pvs=21) <br> - **Team meeting:** clarify how the chatbot interacts with the database, security measures, and **DB access restrictions**. <br> - Propose replacing **RAG with a DynamoDB cache** to reduce costs compared to OpenSearch. | 24/10/2025 | 24/10/2025 | Internal Notion, AWS Blog |



### Week 7 Achievements:

* Gained better understanding of AWS architecture deployment processes and resource optimization (downscaling).  
* Completed review of core AWS services, reinforcing foundational knowledge.  
* Redrew the project architecture diagram and produced an estimated cost.  
* Defined an initial direction for the Text2SQL chatbot (flow, logic, DB access limits).  
* Successfully deployed the chatbot following the AWS Blog guide.  
* Analyzed and proposed replacing RAG with a DynamoDB-based cache to save costs.  
* Increased awareness of database security and access control when a chatbot operates on data.