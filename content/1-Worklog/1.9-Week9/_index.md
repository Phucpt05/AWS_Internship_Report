---
title: "Week 9 Worklog"
date: "2025-10-01"
weight: 9
chapter: false
pre: " <b> 1.9. </b> "
---
{{% notice warning %}} 
⚠️ **Note:** The following information is for reference purposes only. Please **do not copy verbatim** for your own report, including this warning.
{{% /notice %}}

### Week 9 Objectives:

* Understand the core concept of **Serverless architecture** on AWS.  
* Learn to create and deploy **Lambda Functions**, and connect them with **API Gateway**.  
* Explore event-driven workflows using **SNS, SQS**, and **Step Functions**.  
* Practice integrating multiple AWS services in an automated event pipeline.  

### Tasks to be carried out this week:
| Day | Task | Start Date | Completion Date | Reference Material |
| --- | ---- | ----------- | ---------------- | ------------------ |
| 1 | - Learn about AWS Lambda basics: Function creation, handler, and permissions. <br> - **Practice:** Deploy first Lambda function using console and test invocation. | 11/11/2025 | 11/11/2025 | [AWS Lambda Docs](https://docs.aws.amazon.com/lambda/) |
| 2 | - Connect Lambda with **API Gateway** to expose RESTful endpoints. <br> - Test GET/POST requests using Postman. | 11/12/2025 | 11/12/2025 | [API Gateway Overview](https://docs.aws.amazon.com/apigateway/) |
| 3 | - Study **SNS** (Simple Notification Service). <br> - **Practice:** Create SNS topic and subscribe via email. | 11/13/2025 | 11/13/2025 | [AWS SNS Docs](https://docs.aws.amazon.com/sns/) |
| 4 | - Learn **SQS** (Simple Queue Service) for message queuing. <br> - **Practice:** Send and receive messages using AWS Console and connect SQS to Lambda. | 11/14/2025 | 11/14/2025 | [AWS SQS Docs](https://docs.aws.amazon.com/sqs/) |
| 5 | - Explore **Step Functions** for orchestrating workflows. <br> - **Practice:** Build a simple flow integrating Lambda, SQS, and SNS. <br> - Clean up serverless resources after testing. | 11/15/2025 | 11/15/2025 | [AWS Step Functions Docs](https://docs.aws.amazon.com/step-functions/) |

### Week 9 Achievements:

* Built and deployed first **AWS Lambda Function** and understood its execution model and permissions.  
* Successfully integrated **API Gateway** with Lambda to expose a RESTful endpoint, tested via Postman and AWS Console.  
* Implemented **SNS topic** and verified subscription via email notifications.  
* Connected **SQS queue** to Lambda to process messages asynchronously.  
* Designed and executed a **Step Functions workflow** linking multiple serverless services (SNS → Lambda → SQS).  
* Practiced cleaning up AWS serverless resources to prevent unexpected usage costs.  
* Strengthened understanding of **event-driven architecture** and how AWS services communicate through triggers and events.  
