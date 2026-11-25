---
title: "Worklog Tuần 6"
date: 2026-10-19
weight: 1
chapter: false
pre: " <b> 1.6 </b> "
---
### Mục tiêu tuần 6:

- Thiết kế system prompt và quy tắc ngữ cảnh cho chatbot.
- Thiết kế schema dữ liệu cho cơ sở tri thức pháp lý.
- Chuẩn bị bộ câu hỏi mẫu để kiểm thử chất lượng câu trả lời.

### Các công việc cần triển khai trong tuần này:

| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | --------- | ------------ | --------------- | -------------- |
| 2 | Đọc cấu trúc Nghị định 13/2023/NĐ-CP. Chọn các điều luật chính: dữ liệu cá nhân, sự đồng ý, quyền của chủ thể dữ liệu, tiếp thị, xử lý vi phạm. | 19/10/2026 | 19/10/2026 |  |
| 3 | Tạo tài khoản và API key Groq, làm quen với Playground. Viết system prompt theo vai trò: trả lời tiếng Việt, trích dẫn điều luật, kèm lưu ý miễn trừ. | 20/10/2026 | 20/10/2026 | Groq Docs |
| 4 | Thêm ràng buộc chỉ trả lời dựa trên ngữ cảnh được cung cấp và câu trả lời dự phòng khi thiếu căn cứ pháp lý. Thử với câu hỏi ngoài phạm vi (ví dụ về thuế). | 21/10/2026 | 21/10/2026 | Groq Docs |
| 5 | Thiết kế schema bảng LegalArticles gồm id, law_name, article_number, content, keywords. Xác định cách ghép prompt: system prompt + ngữ cảnh pháp lý + câu hỏi, giới hạn số điều luật và độ dài. | 22/10/2026 | 22/10/2026 | AWS Docs: DynamoDB |
| 6 | Soạn bộ câu hỏi mẫu gồm câu đúng phạm vi, câu ngoài phạm vi và câu tình huống thực tế, rồi chạy thử trên Playground. Chỉnh sửa và chốt mẫu prompt cuối cùng. | 23/10/2026 | 23/10/2026 | Groq Docs |

### Kết quả đạt được tuần 6:

- Hiểu cấu trúc chính của Nghị định 13/2023 và chọn được các điều luật cần đưa vào chatbot.
- Viết được system prompt và các ràng buộc ngữ cảnh, có câu trả lời dự phòng.
- Thiết kế xong schema LegalArticles và cách ghép prompt.
- Có bộ câu hỏi mẫu để dùng cho các đợt kiểm thử sau.