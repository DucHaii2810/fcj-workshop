---
title : "Giới thiệu"
date : 2026-11-23
weight : 1
chapter : false
pre : " <b> 5.1. </b> "
---

### Tổng quan

**AI Legal & Security Assistant** là trợ lý tư vấn pháp lý sơ bộ cho doanh nghiệp, tập trung vào Nghị định 13/2023/NĐ-CP (bảo vệ dữ liệu cá nhân). Người dùng nhập câu hỏi hoặc một tình huống thực tế; hệ thống tra cứu các điều luật liên quan trong cơ sở dữ liệu, sau đó mô hình ngôn ngữ lớn phân tích câu hỏi chỉ dựa trên các điều luật đó.

Hệ thống không phải luật sư và không đưa ra kết luận pháp lý chính thức. Nếu cơ sở dữ liệu thiếu căn cứ, hệ thống phải nói rõ.

Hệ thống xây dựng trên kiến trúc serverless với các thành phần:
- **Giao diện** – trang web tĩnh (`index.html`) host trên Amazon S3 (static website hosting)
- **Cổng API** – Amazon API Gateway (CORS và chuẩn hóa lỗi)
- **Backend** – AWS Lambda (Python): truy xuất điều luật và gọi LLM
- **Cơ sở tri thức** – Amazon DynamoDB (bảng `LegalArticles`)
- **LLM** – Groq API (`qwen/qwen3.8-27b`), dịch vụ bên ngoài AWS
- **Giám sát** – Amazon CloudWatch

![alt text](architecture-1.png)
