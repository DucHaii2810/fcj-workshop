---
title: "Week 9 Worklog"
date: 2026-11-09
weight: 1
chapter: false
pre: " <b> 1.9. </b> "
---
### Week 9 Objectives:

- Strengthen system security and set up monitoring.
- Check answer quality and accuracy of legal content.

### Tasks to be implemented this week:

| Day | Task | Start Date | Completion Date | Reference Source |
| --- | --------- | ------------ | --------------- | -------------- |
| 2 | Configure throttling for stage v1. Send multiple consecutive requests to confirm the API returns HTTP 429. | 9/11/2026 | 9/11/2026 | AWS Docs: API Gateway |
| 3 | Set CloudWatch log retention to 7 days. View Lambda metrics, create an alarm for errors, and receive notifications via SNS email. | 10/11/2026 | 10/11/2026 | AWS Docs: CloudWatch |
| 4 | Run test question set including prompt injection and out-of-scope questions. Adjust system prompt and keywords based on results. | 11/11/2026 | 11/11/2026 | Groq Docs |
| 5 | Cross-check legal articles in DynamoDB against official texts. Learn about new laws (such as the Personal Data Protection Law 2025) and note impacts. | 12/11/2026 | 12/11/2026 |  |
| 6 | Create a cost estimate table using AWS Pricing Calculator. List cost optimization measures. | 13/11/2026 | 13/11/2026 | AWS Pricing Calculator |

### Achieved results of Week 9:

- Configured throttling and confirmed API returns 429 when called excessively.
- Set up log retention and Lambda error alert alarm via email.
- Tested prompt injection, improved system prompt based on results.
- Verified legal content and grasped changes from new laws.
- Completed cost estimate and list of optimization measures.