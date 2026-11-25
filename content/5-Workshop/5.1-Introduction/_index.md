---
title : "Introduction"
date : 2026-11-23
weight : 1 
chapter : false
pre : " <b> 5.1. </b> "
---
### Overview

**AI Legal & Security Assistant** is a preliminary legal advisory assistant for enterprises, focusing on Decree 13/2023/ND-CP (personal data protection). Users enter a question or a real-world scenario; the system retrieves relevant legal articles from the database, and then a large language model analyzes the question based strictly on those articles.

The system is not a lawyer and does not provide official legal conclusions. If the database lacks legal basis, the system must clearly state so.

The system is built on a serverless architecture with the following components:
- **Frontend** – static website (`index.html`) hosted on Amazon S3 (static website hosting)
- **API Gateway** – Amazon API Gateway (CORS and error standardization)
- **Backend** – AWS Lambda (Python): retrieves legal articles and calls the LLM
- **Knowledge Base** – Amazon DynamoDB (`LegalArticles` table)
- **LLM** – Groq API (`qwen/qwen3.8-27b`), an external service outside AWS
- **Monitoring** – Amazon CloudWatch

![overview](/images/5-Workshop/5.1-Workshop-overview/diagram1.png)