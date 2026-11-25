---
title: "Worklog Tuần 8"
date: 2026-11-02
weight: 1
chapter: false
pre: " <b> 1.8. </b> "
---
### Mục tiêu tuần 8:

- Xây dựng và kiểm thử backend gồm Lambda, Groq API và API Gateway.
- Chuẩn hóa việc xử lý lỗi và rà soát bảo mật.

### Các công việc cần triển khai trong tuần này:

| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | --------- | ------------ | --------------- | -------------- |
| 2 | Tạo Lambda legal-ai-chat-lambda (Python 3.12) với execution role, đặt timeout 30 giây và biến môi trường GROQ_API_KEY. Viết hàm retrieve_legal_context để chọn điều luật theo từ khóa. | 02/11/2026 | 02/11/2026 | AWS Docs: Lambda |
| 3 | Viết phần ghép prompt và gọi Groq API. Tạo HTTP API LegalChatAPI với route POST /chat, bật CORS và deploy stage v1. | 03/11/2026 | 03/11/2026 | AWS Docs: API Gateway |
| 4 | Test bằng curl với câu hỏi mẫu, câu hỏi rỗng (400) và câu hỏi ngoài phạm vi. Xem log CloudWatch của từng request. | 04/11/2026 | 04/11/2026 | AWS Docs: CloudWatch |
| 5 | Thêm kiểm tra đầu vào và chuẩn hóa mã lỗi 400, 429, 502, 504, 500. Sửa các lỗi phát hiện được trong quá trình test. | 05/11/2026 | 05/11/2026 | AWS Docs: Lambda |
| 6 | Rà soát bảo mật: không ghi log câu hỏi người dùng, bảo vệ API key, giữ quyền tối thiểu. Ghi lại các điểm cần cải thiện cho giai đoạn sau. | 06/11/2026 | 06/11/2026 | AWS Docs: Well-Architected Framework |

### Kết quả đạt được tuần 8:

- Hoàn thành logic RAG trong Lambda và gọi được Groq API.
- Đưa backend ra ngoài qua API Gateway với CORS.
- Test được cả trường hợp thành công lẫn các trường hợp lỗi bằng curl.
- Chuẩn hóa mã lỗi và rà soát bảo mật cho backend.