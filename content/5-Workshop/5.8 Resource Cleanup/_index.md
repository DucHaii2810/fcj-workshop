---
title : "Clean up"
date : 2026-11-23
weight : 8
chapter : false
pre : " <b> 5.8. </b> "
---
### Resource Cleanup Order

Delete resources in the following order to avoid dependency errors and unexpected charges:

1. S3 bucket (`ai-legal-assistant-frontend-hau`)
![alt text](5-8-01.png)

2. API in API Gateway (`LegalChatAPI`)
![alt text](5-8-02.png)

3. Lambda function (`legal-ai-chat-lambda`) and its CloudWatch log group
![alt text](5-8-03.png)
![alt text](5-8-04.png)

4. DynamoDB table `LegalArticles`
![alt text](5-8-05.png)

5. IAM role created for Lambda (`legal-ai-chat-role`)
![alt text](5-8-06.png)

6. Revoke the Groq API key in Groq Console 
![alt text](5-8-07.png)