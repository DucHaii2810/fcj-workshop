---
title: "Week 4 Worklog"
date: 20226-10-05
weight: 1
chapter: false
pre: " <b> 1.4. </b> "
---
### Week 4 Objectives:

- Practice deeply with Lambda, API Gateway, CloudWatch, and DynamoDB.
- Build a small end-to-end serverless API.
- Learn about load balancing and Auto Scaling to compare with the serverless approach.

### Tasks to be implemented this week:

| Day | Task | Start Date | Completion Date | Reference Source |
| --- | --------- | ------------ | --------------- | -------------- |
| 2 | Study Lambda thoroughly: Python runtime, handler, environment variables, memory, and timeout. Practice reading Lambda logs. | 05/10/2026 | 05/10/2026 | AWS Docs: Lambda |
| 3 | Compare REST API and HTTP API in API Gateway. Create an HTTP API integrated with Lambda, learn about route, stage, and CORS. | 06/10/2026 | 06/10/2026 | AWS Docs: API Gateway |
| 4 | Create a DynamoDB table, practice put, get, scan, query via console and boto3. Attach least-privilege permissions for Lambda when accessing DynamoDB. | 07/10/2026 | 07/10/2026 | AWS Docs: DynamoDB |
| 5 | Learn CloudWatch: log group, log retention period, Invocations/Errors/Duration metrics. Create an alarm for Lambda errors and send notifications via SNS email. | 08/10/2026 | 08/10/2026 | AWS Docs: CloudWatch |
| 6 | Do a small lab with Lambda + API Gateway + DynamoDB, test with curl, then clean up resources. Learn ELB and EC2 Auto Scaling at a conceptual level to compare with serverless architecture. | 09/10/2026 | 09/10/2026 | AWS Docs: Elastic Load Balancing |

### Achieved results of Week 4:

- Configured Lambda with environment variables, memory, timeout, and read logs.
- Created an HTTP API integrated with Lambda, understood route, stage, CORS.
- Read/wrote DynamoDB data using boto3 with least privilege.
- Created a CloudWatch alarm and received alerts via email.
- Completed the serverless API lab, understood the difference between serverless and the EC2 + load balancer model.