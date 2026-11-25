---
title: "Worklog Tuần 9"
date: 2026-11-09
weight: 1
chapter: false
pre: " <b> 1.9 </b> "
---
### Mục tiêu tuần 9:

- Tăng cường an toàn cho hệ thống và thiết lập giám sát.
- Kiểm tra chất lượng câu trả lời và độ chính xác của nội dung pháp lý.

### Các công việc cần triển khai trong tuần này:

| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | --------- | ------------ | --------------- | -------------- |
| 2 | Cấu hình throttling cho stage v1. Gửi nhiều request liên tiếp để xác nhận API trả về HTTP 429. | 09/11/2026 | 09/11/2026 | AWS Docs: API Gateway |
| 3 | Đặt thời gian lưu log CloudWatch là 7 ngày. Xem metric của Lambda, tạo alarm cho lỗi và nhận thông báo qua SNS email. | 10/11/2026 | 10/11/2026 | AWS Docs: CloudWatch |
| 4 | Chạy bộ câu hỏi kiểm thử gồm prompt injection và câu hỏi ngoài phạm vi. Chỉnh lại system prompt và từ khóa theo kết quả. | 11/11/2026 | 11/11/2026 | Groq Docs |
| 5 | Đối chiếu các điều luật trong DynamoDB với văn bản chính thức. Tìm hiểu các luật mới (như Luật Bảo vệ dữ liệu cá nhân 2025) và ghi chú ảnh hưởng. | 12/11/2026 | 12/11/2026 |  |
| 6 | Lập bảng ước tính chi phí bằng AWS Pricing Calculator. Liệt kê các biện pháp tối ưu chi phí. | 13/11/2026 | 13/11/2026 | AWS Pricing Calculator |

### Kết quả đạt được tuần 9:

- Cấu hình throttling và xác nhận API trả 429 khi bị gọi quá nhiều.
- Thiết lập được log retention và alarm cảnh báo lỗi Lambda qua email.
- Kiểm thử prompt injection, cải thiện system prompt theo kết quả.
- Xác minh nội dung pháp lý và nắm được thay đổi về luật mới.
- Hoàn thành bản ước tính chi phí và danh sách biện pháp tối ưu.

