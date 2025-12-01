---
title: "Blog 3"
date: "2025-09-09"
weight: 1
chapter: false
pre: " <b> 3.3. </b> "
---

# AWS Weekly Roundup: Amazon S3 Express One Zone price cuts, Pixtral Large on Amazon Bedrock, Amazon Nova Sonic, and more (April 14, 2025)

by Elizabeth Fuentes | on 14 APR 2025| in [Amazon Aurora](https://aws.amazon.com/blogs/aws/category/database/amazon-aurora/), [Amazon Bedrock](https://aws.amazon.com/blogs/aws/category/artificial-intelligence/amazon-machine-learning/amazon-bedrock/), [Amazon Bedrock Agents](https://aws.amazon.com/blogs/aws/category/artificial-intelligence/amazon-machine-learning/amazon-bedrock/amazon-bedrock-agents/), [Amazon Bedrock Guardrails](https://aws.amazon.com/blogs/aws/category/artificial-intelligence/amazon-machine-learning/amazon-bedrock/amazon-bedrock-guardrails/), [Amazon Bedrock Prompt Management](https://aws.amazon.com/blogs/aws/category/artificial-intelligence/amazon-machine-learning/amazon-bedrock/amazon-bedrock-prompt-management/), [Amazon CloudWatch](https://aws.amazon.com/blogs/aws/category/management-tools/amazon-cloudwatch/), [Amazon Nova](https://aws.amazon.com/blogs/aws/category/artificial-intelligence/amazon-machine-learning/amazon-bedrock/amazon-nova/), [Amazon Personalize](https://aws.amazon.com/blogs/aws/category/artificial-intelligence/amazon-personalize/), [Amazon SageMaker](https://aws.amazon.com/blogs/aws/category/artificial-intelligence/sagemaker/), [Announcements](https://aws.amazon.com/blogs/aws/category/post-types/announcements/), [AWS Step Functions](https://aws.amazon.com/blogs/aws/category/application-services/aws-step-functions/), [Launch](https://aws.amazon.com/blogs/aws/category/news/launch/), [News](https://aws.amazon.com/blogs/aws/category/news/), [Storage](https://aws.amazon.com/blogs/aws/category/storage/)

The Amazon Web Services (AWS) Summit 2025 season launched this week, starting with the [Paris Summit](https://aws.amazon.com/events/summits/paris/). These free events bring together the global cloud computing community for learning and collaboration. [AWS Community Day Romania](https://romania.awscommunity.dev/), held on April 11th, showcased how the local community creates opportunities for collective growth and inclusion.

![Image from AWS Summit Paris 2025](/images/3-BlogsTranslated/3.3-Blog3/1.png)

<u><b>Last week’s launches</b></u>

[Announcing up to 85% price reductions for Amazon S3 Express One Zone — S3 Express One Zone](https://aws.amazon.com/es/blogs/aws/up-to-85-price-reductions-for-amazon-s3-express-one-zone/), a high-performance storage class, now has reduced storage prices by 31 percent, PUT request prices by 55 percent, and GET request prices by 85 percent. In addition, S3 Express One Zone has reduced the per-GB charges for data uploads and retrievals by 60 percent. These charges now apply to all bytes transferred rather than just portions of requests greater than 512 KB. Here is a price reduction table in the US East (N. Virginia) AWS Region:

| Price                                 | Previous                                 | New                           | Price reduction |
|----------------------------------------|------------------------------------------|-------------------------------|-----------------|
| **Storage**<br/>(per GB-Month)         | $0.16                                    | $0.11                         | 31%             |
| **Writes**<br/>(PUT requests)          | $0.0025 per 1,000 requests up to 512 KB  | $0.00113 per 1,000 requests   | 55%             |
| **Reads**<br/>(GET requests)           | $0.0002 per 1,000 requests up to 512 KB  | $0.00003 per 1,000 requests   | 85%             |
| **Data upload**<br/>(per GB)           | $0.008                                   | $0.0032                       | 60%             |
| **Data retrievals**<br/>(per GB)       | $0.0015                                  | $0.0006                       | 60%             |

[AWS announces Pixtral Large 25.02 model in Amazon Bedrock serverless — Pixtral Large 25.02](https://aws.amazon.com/blogs/aws/aws-announces-pixtral-large-25-02-model-in-amazon-bedrock-serverless/), developed by [Mistral AI](https://mistral.ai/), combines advanced vision and language understanding, boasting a 128K context window and multilingual capabilities. This agent-centric design simplifies integration with existing systems. Prompt adherence improves reliability when working with [Retrieval Augmented Generation (RAG)](https://aws.amazon.com/what-is/retrieval-augmented-generation/) applications and large context scenarios.

![](/images/3-BlogsTranslated/3.3-Blog3/2.png)

[Introducing Amazon Nova Sonic: Human-like voice conversations for generative AI applications — Amazon Nova Sonic](https://aws.amazon.com/blogs/aws/introducing-amazon-nova-sonic-human-like-voice-conversations-for-generative-ai-applications/), the newest addition to the [Amazon Nova family of foundation models (FMs), now available in Amazon Bedrock](https://aws.amazon.com/nova/), enables human-like voice conversations for applications. It unifies speech and text processing into one model, reducing complexity and enhancing natural interactions. Start today with the [Amazon Nova model cookbook repository.](https://github.com/aws-samples/amazon-nova-samples)

<video style="width:100%;" controls>
  <source src="/images/3-BlogsTranslated/3.3-Blog3/Nova-s2s-blog.mp4" type="video/mp4">
</video>

[Amazon Bedrock Guardrails enhances generative AI application safety with new capabilities](https://aws.amazon.com/blogs/aws/amazon-bedrock-guardrails-enhances-generative-ai-application-safety-with-new-capabilities/) — [Amazon Bedrock Guardrails](https://aws.amazon.com/bedrock/guardrails/) introduces new capabilities to enhance generative AI application safety, including multimodal toxicity detection, enhanced Personally Identifiable Information (PII) protection, [AWS Identity and Access Management (AWS IAM)](https://aws.amazon.com/iam/) policy enforcement, selective guardrail application, and monitor mode for pre-deployment analysis.

[AWS App Studio introduces a prebuilt solutions catalog and cross-instance Import and Export](https://aws.amazon.com/about-aws/whats-new/2025/04/aws-app-studio-prebuilt-solutions-catalog-import-export/) — This is a prebuilt solutions catalog with ready-to-use applications and patterns and cross-instance Import and Export functionality. These features help you streamline development applications, reducing setup time to under 15 minutes. Learn more about this in the [AWS App Studio introduces a prebuilt solutions catalog and cross-instance Import and Export blog.](https://aws.amazon.com/blogs/machine-learning/aws-app-studio-introduces-a-prebuilt-solutions-catalog-and-cross-instance-import-and-export/)

[Amazon Nova Reel 1.1: Featuring up to 2-minutes multi-shot videos](https://aws.amazon.com/es/blogs/aws/amazon-nova-reel-1-1-featuring-up-to-2-minutes-multi-shot-videos/) — [Amazon Nova Reel](https://aws.amazon.com/nova/) 1.1 enhances video generation through [Amazon Bedrock](https://aws.amazon.com/bedrock/) with support for 2-minute multi-shot videos. You can now create content using either single prompts for automatic generation or custom prompts for individual shots, offering flexible options for marketing and social media content creation.

<video style="width:100%;" controls>
  <source src="/images/3-BlogsTranslated/3.3-Blog3/awsnews-1526_Underwater Racoon.mp4" type="video/mp4">
</video>

[AWS IAM Identity Center now offers improved error messages and AWS CloudTrail logging for provisioning issues](https://aws.amazon.com/about-aws/whats-new/2025/02/aws-iam-identity-center-error-messages-cloudtrail-logging-provisioning-issues/) — [AWS Identity and Access Management (IAM) Identity Center](https://aws.amazon.com/iam/identity-center/) has enhanced its service with improved error messages and AWS CloudTrail logging capabilities. These updates help users better troubleshoot synchronization issues when managing workforce identities across [AWS accounts](https://aws.amazon.com/organizations/getting-started/best-practices/) and applications, while enabling automated monitoring and auditing of provisioning problems.

[AWS WAF Console adds new top insights visualizations in additional regions](https://aws.amazon.com/about-aws/whats-new/2025/02/aws-waf-console-top-insights-visualizations-additional-regions/) — The [AWS WAF](https://docs.aws.amazon.com/waf/latest/developerguide/waf-chapter.html) console now offers enhanced traffic visualization features in [AWS GovCloud (US) Regions.](https://aws.amazon.com/govcloud-us/) The new all traffic dashboard includes top insights based on logs from [Amazon CloudWatch](https://aws.amazon.com/cloudwatch/), helping customers analyze traffic patterns, identify security threats, and optimize WAF configurations through detailed metrics.

[AWS Step Functions expands data source and output options for Distributed Map](https://aws.amazon.com/about-aws/whats-new/2025/02/aws-step-functions-data-source-output-option-distributed-map/) — [AWS Step Functions](https://aws.amazon.com/step-functions/) enhances Distributed Map with expanded data source support, including JSONL and various delimited file formats from [Amazon Simple Storage Service (Amazon S3).](https://aws.amazon.com/s3/) The update also adds new output transformation options, enabling more flexible parallel processing workflows and better integration with downstream systems.

[Amazon CloudWatch now provides lock contention diagnostics for Aurora PostgreSQL](https://aws.amazon.com/about-aws/whats-new/2025/02/amazon-cloudwatch-lock-contention-diagnostics-aurora-postgresql/) — [Amazon CloudWatch Database Insights](https://docs.aws.amazon.com/AmazonCloudWatch/latest/monitoring/Database-Insights.html) introduces lock contention diagnostics for [Amazon Aurora PostgreSQL](https://aws.amazon.com/rds/aurora/postgresql-features/) in Advanced mode. The feature visualizes blocking and waiting sessions, helping users identify root causes of lock contention issues, with 15-month historical data retention for comprehensive troubleshooting.
Get updated with all the announcements of AWS on the [What’s New with AWS?](https://aws.amazon.com/new/) page.

<b><u>Other AWS blog posts</u></b>

[**Reduce ML training costs with Amazon SageMaker HyperPod**](https://aws.amazon.com/blogs/machine-learning/reduce-ml-training-costs-with-amazon-sagemaker-hyperpod/) — [Amazon SageMaker HyperPod](https://aws.amazon.com/sagemaker/hyperpod/) addresses hardware failures in large-scale [Machine Learning (ML)](https://aws.amazon.com/what-is/machine-learning/) model training by automatically detecting and replacing faulty instances. The solution reduces downtime from 280 to 40 minutes per failure, potentially saving 32% of training time for large clusters. For a 10-million GPU-hour training job, this translates to $25.6M in cost savings.

[**Model customization, RAG, or both: A case study with Amazon Nova**](https://aws.amazon.com/blogs/machine-learning/model-customization-rag-or-both-a-case-study-with-amazon-nova/) — A study comparing model customization with fine-tuning and [Retrieval Augmented Generation (RAG)](https://aws.amazon.com/what-is/retrieval-augmented-generation/) approaches with [Amazon Nova models.](https://aws.amazon.com/ai/generative-ai/nova/) Key findings show combining both methods yields best results: RAG works well for dynamic data and domain insights, while fine-tuning excels in specialized tasks and latency reduction.

[**Generate user-personalized communication with Amazon Personalize and Amazon Bedrock**](https://aws.amazon.com/blogs/machine-learning/generate-user-personalized-communication-with-amazon-personalize-and-amazon-bedrock/) — [Amazon Personalize](https://aws.amazon.com/personalize/) and Amazon Bedrock work together to create personalized marketing emails. Learn how to create personalized user communications by combining Amazon Personalize for movie recommendations with Amazon Bedrock for generating tailored email content based on user preferences and demographics.

![](/images/3-BlogsTranslated/3.3-Blog3/3.png)

[**Implement human-in-the-loop confirmation with Amazon Bedrock Agents**](https://aws.amazon.com/blogs/machine-learning/implement-human-in-the-loop-confirmation-with-amazon-bedrock-agents/) — When implementing human validation in [Amazon Bedrock Agents](https://aws.amazon.com/bedrock/agents/), developers have two primary frameworks at their disposal: user confirmation and return of control (ROC). Using an HR application example, user confirmation allows simple yes/no validation before executing actions, while ROC enables users to modify parameters before execution.

[**Multi-LLM routing strategies for generative AI applications on AWS**](https://aws.amazon.com/blogs/machine-learning/multi-llm-routing-strategies-for-generative-ai-applications-on-aws/) — Learn how to implement multi-[Large Language Model (LLM)](https://aws.amazon.com/what-is/large-language-model/) routing strategies for [AWS generative AI applications](https://aws.amazon.com/what-is/generative-ai/) using static routing, dynamic routing with Amazon Bedrock, or custom solutions for optimal model selection and cost efficiency.

![](/images/3-BlogsTranslated/3.3-Blog3/4.png)

Here are my personal favorites posts from [<u>community.aws</u>](https://builder.aws.com/):

[Building a RAG System for Video Content Search and Analysis](https://builder.aws.com/content/2stievBb8ZuQtebTPNm8kC7ul0c/building-a-rag-system-for-video-content-search-and-analysis) — In this blog, I’ll show you how to build a RAG system that makes video content searchable and analyzable. Unlocking video content has never been more crucial in today’s digital landscape. Whether you’re managing educational materials, corporate training, or entertainment content, the ability to search and analyze video content efficiently can transform how we interact with multimedia resources.

[Build Serverless GenAI Apps Faster with Amazon Q Developer CLI Agent](https://builder.aws.com/content/2uVl543Irg1pNRSkGY4yvth7Tmw/build-serverless-genai-apps-faster-with-amazon-q-developer-cli-agent) — [Amazon Q Developer](https://aws.amazon.com/q/) CLI Agent enables rapid serverless GenAI app development. With one prompt, it generates infrastructure code, Lambda functions, and integrates with Claude 3 Haiku on Amazon Bedrock.

[Speech-to-Speech AI: From Dr. Sbaitso to Amazon Nova Sonic](http://community.aws/content/2vEZph0MzNXYJJSrNkgN9V2kYLY/speech-to-speech-ai-from-dr-sbaitso-to-amazon-nova-sonic) — The evolution of speech-to-speech AI, from Dr. Sbaitso (1990s) to Amazon Nova Sonic. New AWS service enables real-time bidirectional conversations through Amazon Bedrock for more natural applications.

[Setup Model Context Protocol (MCP) using Amazon Bedrock](https://builder.aws.com/content/2vPB0cvCY08EWYleQ8vcMCOvQVg/run-local-mcp-desktop-client-using-amazon-bedrock) — A guide to setting up the MCP (Model Context Protocol) desktop client to work with Amazon Bedrock models, enabling seamless integration between AI applications and external tools using the Goose client.

<b><u>Upcoming AWS events</u></b>

Check your calendars and sign up for these upcoming AWS events:

[AWS GenAI Lofts — GenAI Lofts](https://aws.amazon.com/startups/lp/aws-gen-ai-lofts) are available around the world, offering collaborative spaces and immersive experiences for startups and developers. You can join in-person [GenAI Loft San Francisco](https://aws.amazon.com/startups/events?tag=GENAI_LOFT_SAN_FRANCISCO) events such as [GenAI in EdTech: A Hands-On Workshop](https://aws.amazon.com/startups/events/genai-in-edtech-a-hands-on-workshop) (April 15), and [Unstructured Data Meetup SF](https://aws.amazon.com/startups/events/built-on-bedrock-demo-nights-sf-202504) (April 16). Find your nearest event at [GenAI Lofts.](https://aws.amazon.com/events/genai-lofts/)

[AWS Summits](https://aws.amazon.com/events/summits/) — Join free online and in-person events that bring the cloud computing community together to connect, collaborate, and learn about AWS. Register in your nearest city: [Amsterdam](https://aws.amazon.com/events/summits/amsterdam/) (April 16), [London](https://aws.amazon.com/events/summits/london/) (April 30), and [Poland](https://aws.amazon.com/events/summits/poland/) (May 5).

[AWS re:Inforce](https://reinforce.awsevents.com/) — AWS re:Inforce (June 16–18) in Philadelphia, PA, is our annual learning event devoted to all things AWS cloud security. [Registration is open](https://reinforce.awsevents.com/). Be ready to join more than 5,000 security builders and leaders.

[AWS Community Days](https://aws.amazon.com/events/community-day/) — Join community-led conferences featuring technical discussions, workshops, and hands-on labs driven by expert AWS users and industry leaders from around the world. [Upcoming Community Days](https://aws.amazon.com/events/community-day/) are scheduled for April 19 in [Turkey](https://aws.cloudturkey.io/), and on April 29 in [Prague](https://awscommunityday.cz/2025/), with [Jeff Barr](https://www.linkedin.com/in/jeffbarr/) as Opening Keynote Speaker.

You can browse all upcoming [in-person and virtual events](https://aws.amazon.com/events).

Create your [AWS Builder ID](https://profile.aws.amazon.com/) and reserve your alias. Builder ID is a universal login credential that gives you access—beyond the AWS Management Console—to AWS tools and resources, including over 600 free training courses, community features, and developer tools such as Amazon Q Developer.
That’s all for this week. Stay tuned for next week’s Weekly Roundup!

— [Eli](https://www.linkedin.com/in/lizfue/)

<i>Thanks to Andra Somesan for the AWS Community Romania photo and Thembile Martis for the AWS Paris Summit photo.</i>

<i>This post is part of our Weekly Roundup series. Check back each week for a quick roundup of interesting news and announcements from AWS!</i>

<table>
    <tr>
        <td style="vertical-align:top; width:110px; text-align:center;">
            <img src="/images/3-BlogsTranslated/3.3-Blog3/elizabeth.jpeg" alt="Elizabeth Fuentes" style="width:100px; border-radius:8px; display:block; margin:0 auto 8px auto;"/>
            <div style="font-weight:bold; margin-top:4px;">Elizabeth Fuentes</div>
        </td>
        <td style="vertical-align:top; padding-left:20px;">
            My mission is to break down complex concepts into easily digestible explanations, inspiring developers to continually expand their skills and knowledge. Through conferences, tutorials, and online resources, I share my expertise with the global developer community, providing them with the tools and confidence to reach their full potential. With a hands-on approach and a commitment to simplifying the complex, I strive to be a catalyst for growth and learning in the world of AWS technology.
        </td>
    </tr>
</table>

