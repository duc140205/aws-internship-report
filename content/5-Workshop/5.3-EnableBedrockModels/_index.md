---
title : "Enable Bedrock Models"
date :  "2025-09-09" 
weight : 3
chapter : false
pre : " <b> 5.3. </b> "
---

## Enabling Bedrock Models

Before deploying the solution, you need to enable the required Amazon Bedrock models in your AWS account.

### Steps to Enable Models

1. **Search for Amazon Bedrock** in AWS Console
2. **Access Model catalog** from the left navigation menu
3. **Choose the corresponding model name:**
   - Anthropic Claude 3.5 Sonnet
   - Anthropic Claude 3 Sonnet
   - Anthropic Claude 3 Haiku
   - Amazon Titan Embeddings G1 – Text
4. **Select "Open in playground"** and send a test message to enable each model

{{% notice note %}}
Make sure you enable all four models in the **ap-northeast-1 (Tokyo)** region as the solution is deployed in this region.
{{% /notice %}}

### Verification

After enabling the models, you can verify they are accessible by checking the "Model access" section in the Amazon Bedrock console. All four models should show a status of "Access granted".
