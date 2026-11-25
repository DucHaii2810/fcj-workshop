---
title: "Week 8 Worklog"
date: 2026-11-02
weight: 1
chapter: false
pre: " <b> 1.8 </b> "
---
### Week 8 Objectives:

- Build and test the backend comprising Lambda, Groq API, and API Gateway.
- Standardize error handling and review security.

### Tasks to be implemented this week:

| Day | Task | Start Date | Completion Date | Reference Source |
| --- | --------- | ------------ | --------------- | -------------- |
| 2 | Create Lambda legal-ai-chat-lambda (Python 3.12) with execution role, set 30-second timeout and GROQ_API_KEY environment variable. Write retrieve_legal_context function to select articles by keyword. | 02/11/2026 | 02/11/2026 | AWS Docs: Lambda |
| 3 | Write prompt assembly and call Groq API. Create HTTP API LegalChatAPI with POST /chat route, enable CORS, and deploy stage v1. | 03/11/2026 | 03/11/2026 | AWS Docs: API Gateway |
| 4 | Test with curl using sample questions, empty questions (400), and out-of-scope questions. View CloudWatch logs for each request. | 04/11/2026 | 04/11/2026 | AWS Docs: CloudWatch |
| 5 | Add input validation and standardize error codes 400, 429, 502, 504, 500. Fix bugs found during testing. | 05/11/2026 | 05/11/2026 | AWS Docs: Lambda |
| 6 | Security review: do not log user questions, protect API key, maintain least privilege. Note improvements for later phases. | 06/11/2026 | 06/11/2026 | AWS Docs: Well-Architected Framework |

### Achieved results of Week 8:

- Completed RAG logic in Lambda and called Groq API.
- Exposed backend via API Gateway with CORS.
- Tested both success and error cases using curl.
- Standardized error codes and conducted security review for the backend.