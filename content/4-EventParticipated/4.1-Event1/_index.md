---
title: "Event 1"
date: "2025-09-09"
weight: 1
chapter: false
pre: " <b> 4.1. </b> "
---

# Summary Report: “AWS Cloud Mastery Series #1 - AI/ML/GenAI on AWS”

### Event Objectives

- Provide an overview of AI/ML/GenAI capabilities on AWS and how they can be applied in real-world use cases.

### Speakers

- **Lam Tuan Kiet** – Sr DevOps Engineer, FPT Software  
- **Danh Hoang Hieu Nghi** – AI Engineer, Renova Cloud  
- **Dinh Le Hoang Anh** – Cloud Engineer Trainee, First Cloud AI Journey  
- **Van Hoang Kha** – Community Builder

### Key Highlights

## 1. Generative AI on Amazon Bedrock

**Foundation Models (FMs):**  
AWS supplies a library of fully managed FMs from multiple leading AI providers (Anthropic, OpenAI, Meta, etc.), allowing users to adapt them to various tasks without building models from scratch.

**Prompt Engineering:**  
Understanding how to guide models effectively through different prompting strategies:
  + **Zero-shot:** Model receives only the task description.  
  + **Few-shot:** Model is given a handful of examples to mimic.  
  + **Chain-of-Thought:** Encouraging the model to reveal reasoning steps for more accurate outcomes.

**Retrieval Augmented Generation (RAG):**  
Enhances model outputs by injecting external knowledge:
  + **R – Retrieval:** Pulls relevant data from a knowledge store.  
  + **A – Augmentation:** Adds this data as context in the prompt.  
  + **G – Generation:** Model creates a more grounded and accurate answer.  
  + **Use cases:** Chatbots with knowledge bases, contextual search, and near-real-time summary generation.

**Amazon Titan Embeddings:**  
Lightweight embedding model that turns text into dense vectors for similarity search and RAG workflows, with multilingual support.

**AWS AI Services:** Ready-made AI APIs for common tasks:
  - Rekognition – Image/Video analysis  
  - Translate – Language translation  
  - Textract – Extract text + layout from documents  
  - Transcribe – Speech-to-text  
  - Polly – Text-to-speech  
  - Comprehend – NLP insights  
  - Kendra – Intelligent enterprise search  
  - Lookout – Anomaly detection  
  - Personalize – Recommendation systems  

**Demo Highlight:**  
A simple face-recognition application (AMZPhoto) demonstrating how AI services integrate with user-facing apps.

---


## 2. Amazon Bedrock AgentCore – Building Production-Ready AI Agents

A new framework enabling teams to operate AI agents reliably at scale:
  - Execute and scale agent workflows securely  
  - Manage long-term memory  
  - Grant fine-grained identity & access control  
  - Integrate with tools like Browser Tool, Code Interpreter, Memory Store  
  - Provide observability and auditing  
  - Support popular agent frameworks (CrewAI, LangGraph, LlamaIndex, OpenAI Agents SDK, etc.)

---

### Key Takeaways

- **Bedrock as the central GenAI platform:** Easy access to many FMs in one place.  
- **Prompting + RAG as customization tools:** Improve model relevance with context and examples.  
- **Embeddings for smarter search:** Titan Embeddings boosts retrieval accuracy for knowledge-driven applications.  
- **Pretrained models accelerate development:** No need to build everything manually.  
- **AgentCore reduces deployment complexity:** Handles scaling, memory, identity, and monitoring for agentic systems.

---

### Applying to Work

- The concepts from the session (especially RAG and AgentCore) can be directly aligned with future internal projects involving GenAI-powered features.
- Understanding AWS AI services helps in selecting the right tools for different application needs, speeding up development cycles.
- The knowledge gained about prompt engineering can be applied to improve the performance of AI models in various scenarios.

### Event Experience
- Placed top 5 in the end of event Kahoot Quiz and got a picture with the speakers
- Formed a small collaborative group called **“Mèo Cam Đeo Khăn”**, combining members from “The Ballers” and “Vinhomies”.

#### Some event photos
  
![Event Photo 1](/images/4-EventParticipated/4.1-Event1/kahoot.jpg)
![Event Photo 2](/images/4-EventParticipated/4.1-Event1/ending.jpg)
![Event Photo 3](/images/4-EventParticipated/4.1-Event1/meocam.jpg)

