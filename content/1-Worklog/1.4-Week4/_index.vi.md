---
title: "Worklog Tuần 4"
date: 2026-10-05
weight: 1
chapter: false
pre: " <b> 1.4. </b> "
---
### Mục tiêu tuần 4:

- Thực hành sâu với Lambda, API Gateway, CloudWatch và DynamoDB.
- Xây dựng một API serverless nhỏ hoàn chỉnh từ đầu đến cuối.
- Tìm hiểu cân bằng tải và Auto Scaling để so sánh với hướng serverless.

### Các công việc cần triển khai trong tuần này:

| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | --------- | ------------ | --------------- | -------------- |
| 2 | Tìm hiểu kỹ Lambda: runtime Python, handler, biến môi trường, memory và timeout. Thực hành đọc log của Lambda. | 05/10/2026 | 05/10/2026 | AWS Docs: Lambda |
| 3 | So sánh REST API và HTTP API trong API Gateway. Tạo HTTP API tích hợp Lambda, tim hiểu route, stage và CORS. | 06/10/2026 | 06/10/2026 | AWS Docs: API Gateway |
| 4 | Tạo bảng DynamoDB, thực hành put, get, scan, query bằng console và boto3. Gắn quyền tối thiểu cho Lambda khi truy cập DynamoDB. | 07/10/2026 | 07/10/2026 | AWS Docs: DynamoDB |
| 5 | Tìm hiểu CloudWatch: log group, thời gian lưu log, metric Invocations/Errors/Duration. Tạo alarm cho lỗi Lambda và gửi thông báo qua SNS email. | 08/10/2026 | 08/10/2026 | AWS Docs: CloudWatch |
| 6 | Làm lab nhỏ Lambda + API Gateway + DynamoDB, test bằng curl rồi dọn tài nguyên. Tìm hiểu ELB và EC2 Auto Scaling ở mức khái niệm để so sánh với kiến trúc serverless. | 09/10/2026 | 09/10/2026 | AWS Docs: Elastic Load Balancing |

### Kết quả đạt được tuần 4:

- Cấu hình được Lambda với biến môi trường, memory, timeout và đọc được log.
- Tạo HTTP API tích hợp Lambda, hiễu route, stage, CORS.
- Đọc/ghi dữ liệu DynamoDB bằng boto3 với quyền tối thiểu.
- Tạo được CloudWatch alarm và nhận cảnh báo qua email.
- Hoàn thành lab API serverless, hiểu sự khác nhau giữa serverless và mô hình EC2 + load balancer.