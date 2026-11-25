---
title : "Final Outcomes and Future Directions"
date : 2024-01-01
weight : 6
chapter : false
pre : " <b> 5.7 </b> "
---
### Outcomes
- A complete, auto-scaling serverless backend that, as noted by the team, costs $0 within the AWS Free Tier.
- A working RAG pipeline: each request looks up legal articles from DynamoDB and pairs them with the LLM to produce grounded answers.
- A stable API endpoint ready for the static website and for team members to test.

### Known Limitations
- Keyword lookup may miss relevant legal articles.
- Responses are plain text; there is no structured risk level yet.
- The LLM runs outside AWS and the API has no authentication yet.

### Future Directions
- Structured responses with risk level (`Low` / `Medium` / `High` / `Insufficient evidence`), articles, evidence, and sources.
- Human-confirmed incident reporting with email alerts via Amazon SNS (summary only, no sensitive data).
- Conversation history in DynamoDB with TTL.
- Evaluate Amazon Bedrock and Bedrock Knowledge Bases to keep all data within AWS (check current pricing and supported regions first).