---
title: "Event 2"
date: "2025-09-09"
weight: 1
chapter: false
pre: " <b> 4.2. </b> "
---

# Summary Report: “AWS Cloud Mastery Series #2 – DevOps on AWS”

### Event Objectives

- Provide an introduction to AWS DevOps services and how to design CI/CD pipelines.
- Explore Infrastructure as Code (IaC) concepts and associated tooling.
- Present an overview of containerized workloads on AWS.
- Demonstrate how to achieve effective monitoring and observability using AWS-native services.

### Speakers

- **Truong Quang Tinh** – AWS Community Builder, Platform Engineer (TymeX)  
- **Bao Huynh** – AWS Community Builder  
- **Nguyen Khanh Phuc Thinh** – AWS Community Builder  
- **Tran Dai Vi** – AWS Community Builder  
- **Huynh Hoang Long** – AWS Community Builder  
- **Pham Hoang Quy** – AWS Community Builder  
- **Nghiem Le** – AWS Community Builder  
- **Dinh Le Hoang Anh** – Cloud Engineer Trainee, First Cloud AI Journey

### Key Highlights

### **1. Building a DevOps Foundation**

The speakers highlighted that DevOps is less about job titles and more about adopting habits that improve delivery:  
- Automating repetitive tasks  
- Sharing knowledge across roles  
- Continuously experimenting and learning  
- Tracking measurable outcomes instead of relying on assumptions  

They also shared common pitfalls that early DevOps learners face, such as relying too much on tutorials without building real projects or comparing progress with others instead of focusing on steady improvement.

---

### **2. Infrastructure as Code in Practice**

Rather than sticking to one tool, the speakers compared several IaC approaches:

- **CloudFormation** as AWS’s native template engine  
- **CDK** for developers who prefer writing infrastructure using programming languages  
- **Terraform** for teams working across multiple cloud providers  

The differences between Stacks, Constructs, State files, and abstraction layers were explained using practical examples.

A strong message from this section: infrastructure rebuilt using IaC tends to be *more consistent and maintainable* than anything configured manually.

---

### **3. Containers and Deployment Models**

The container portion took a step-by-step approach, starting with what a Dockerfile represents and how images are created.  
From there, the talk expanded into AWS services:

- **ECR** for storing and scanning container images  
- **ECS & EKS** for orchestration  
- **App Runner** for teams who want to deploy without dealing with cluster management  

The comparison between ECS and EKS helped clarify when each should be used.

---

### **4. Monitoring and Tracing**

The final portion of the event covered AWS CloudWatch and X-Ray:

- CloudWatch as the central source for metrics, dashboards, alarms, and logs  
- X-Ray for visualizing request flows and identifying latency bottlenecks  

The speakers stressed that observability is not something added at the end—it must be integrated into the architecture from the beginning.

---
### Key Takeaways
- DevOps is not just a job title but a mindset and set of habits that improve software delivery.

- Automation, knowledge sharing, continuous experimentation, and measuring outcomes are essential for DevOps success.
Using Infrastructure as Code (IaC) leads to more consistent and maintainable infrastructure compared to manual configuration.

- The choice of IaC tools (CloudFormation, CDK, Terraform) should be based on team needs and project requirements.
Understanding the differences between AWS container services (ECR, ECS, EKS, App Runner) helps in selecting the right solution for each use case.

- Monitoring and observability must be integrated from the beginning, not added as an afterthought, to ensure system stability and quick issue detection.


### Applying to Work

#### Example: AI Chatbot Project on AWS

After attending the event, I will plan to apply DevOps and AWS knowledge to an AI Chatbot project if possible as follows:

- **CI/CD Pipeline Design:** Used AWS CodePipeline to automate the build, test, and deployment process for the chatbot to production, ensuring every code update is tested and deployed automatically.
- **Infrastructure as Code:** Used AWS CDK to define all infrastructure (Lambda, API Gateway, DynamoDB, S3, IAM, etc.) as code, making the system easy to reuse and scale consistently.

By applying DevOps and AWS services, the AI chatbot project can be developed quickly, deployed continuously, and is easy to maintain and scale as needed.


### Event Experience
- Attending the event gave me a practical perspective on how modern organizations implement DevOps on AWS.
The speakers not only shared theoretical knowledge but also provided real-world examples, helping me better understand tools like CloudFormation, CDK, Terraform, and how to operate and deploy containers on AWS.

- The event was also a great opportunity to connect with like-minded peers and learn valuable hands-on experiences from the speakers.
#### Some event photos
![Event Photo 1](/images/4-EventParticipated/4.2-Event2/recap.jpg)
