---
title: "Week 7 Worklog"
date: 2026-10-26
weight: 1
chapter: false
pre: " <b> 1.7 </b> "
---
### Week 7 Objectives:

- Build the legal knowledge base on DynamoDB.
- Configure IAM following the principle of least privilege for Lambda.

### Tasks to be implemented this week:

| Day | Task | Start Date | Completion Date | Reference Source |
| --- | --------- | ------------ | --------------- | -------------- |
| 2 | Check Budget alerts and Free Tier usage. Finalize a shared Region for all resources. Create the LegalArticles table in on-demand mode to avoid unintended charges. | 26/10/2026 | 26/10/2026 | AWS Docs: DynamoDB |
| 3 | Summarize selected legal articles and tag keywords. Cross-check content against official texts. | 27/10/2026 | 27/10/2026 |  |
| 4 | Write a seed script using boto3 batch_writer and load data. Verify data using Explore table items. | 28/10/2026 | 28/10/2026 | AWS Docs: DynamoDB |
| 5 | Create an IAM policy with read-only access to the LegalArticles table plus CloudWatch log write permission. Create execution role legal-ai-chat-role for Lambda and attach the policy. | 29/10/2026 | 29/10/2026 | AWS Docs: IAM |
| 6 | Test reading the table using AWS CLI/boto3, try a write operation to confirm it is denied. Review permissions and remove unnecessary ones. | 30/10/2026 | 30/10/2026 | AWS Docs: IAM |

### Achieved results of Week 7:

- Created the LegalArticles table and loaded legal article data via the seed script.
- Data was cross-checked against official texts.
- Created least-privilege IAM policy and role, confirmed write permission was denied.