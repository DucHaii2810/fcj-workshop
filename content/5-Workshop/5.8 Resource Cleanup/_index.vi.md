---
title : "Dọn dẹp tài nguyên"
date : 2024-01-01
weight : 6
chapter : false
pre : " <b> 5.8. </b> "
---

### Thứ tự dọn dẹp tài nguyên

Xóa tài nguyên theo thứ tự sau để tránh lỗi phụ thuộc và chi phí phát sinh:

1. S3 bucket (`ai-legal-assistant-frontend-hau`)
![alt text](5-8-01.png)

2. API trong API Gateway (`LegalChatAPI`)
![alt text](5-8-02.png)

3. Hàm Lambda (`legal-ai-chat-lambda`) và log group CloudWatch của nó
![alt text](5-8-03.png)
![alt text](5-8-04.png)

4. Bảng DynamoDB `LegalArticles`
![alt text](5-8-05.png)

5. IAM role tạo cho Lambda (`legal-ai-chat-role`) 
![alt text](5-8-06.png)

6. Thu hồi Groq API key trong Groq Console
![alt text](5-8-07.png)