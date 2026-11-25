---
title: "Worklog Tuần 2"
date: 2026-09-21
weight: 1
chapter: false
pre: " <b> 1.2. </b> "
---
### Mục tiêu tuần 2:

- Hiểu AWS IAM và áp dụng nguyên tắc đặc quyền tối thiểu (least privilege).
- Nắm cơ bản về Amazon EC2 và thực hành tạo, kết nối, xóa instance an toàn.
- Làm quen với Amazon S3 và các tính năng lưu trữ cơ bản.
- Tham dự talkshow và rút ra bài học áp dụng cho dự án chatbot của nhóm.

### Các công việc cần triển khai trong tuần này:

| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | --------- | ------------ | --------------- | -------------- |
| 2 | Học IAM: users, groups, roles, policies và nguyên tắc least privilege. Xem lại khuyến nghị bảo mật cho tài khoản root. | 21/9/2026 | 21/9/2026 | AWS Docs: IAM |
| 3 | Tạo IAM user và group, gắn managed policy rồi kiểm tra quyền của từng tài khoản. Viết thử một custom policy dạng JSON và kiểm tra kết quả Allow/Deny. | 22/9/2026 | 22/9/2026 | AWS Docs: IAM |
| 4 | Tìm hiểu IAM Role, thông tin xác thực tạm thời và cách quản lý Access Key an toàn khi dùng CLI. Bật MFA cho IAM user và thử đăng nhập lại. | 23/9/2026 | 23/9/2026 | AWS Docs: IAM |
| 5 | Học EC2: instance type, AMI, key pair, security group và EBS. Tạo một instance Free Tier, kết nối SSH, tạo EBS snapshot rồi terminate để tránh phát sinh phí. | 24/9/2026 | 24/9/2026 | AWS Docs: EC2 |
| 6 | Tạo S3 bucket, upload file, bật versioning và xem lại Block Public Access. Kiểm tra Free Tier và cảnh báo Budget, dọn dẹp toàn bộ tài nguyên của tuần. | 25/9/2026 | 25/9/2026 | AWS Docs: S3 |
| 7 | Tham dự talkshow "The Thinking Behind Building The Bot" (09:00, tầng 26, Bitexco Tower, TP.HCM). Ghi lại các ý chính về cách tư duy và thiết kế một con bot để áp dụng cho dự án. | 26/9/2026 | 26/9/2026 | Sự kiện: Talkshow "The Thinking Behind Building The Bot" |

### Kết quả đạt được tuần 2:

- Hiểu vai trò của IAM users, groups, roles, policies và áp dụng được least privilege.
- Viết và kiểm tra được custom policy JSON, bật MFA cho tài khoản.
- Tạo, kết nối và xóa EC2 instance đúng cách; biết dùng key pair, security group, EBS snapshot.
- Làm quen với S3 bucket, object và versioning.
- Có thói quen dọn tài nguyên và theo dõi Free Tier sau mỗi buổi thực hành.
- Tham dự talkshow và ghi lại các ý có thể áp dụng cho chatbot của nhóm.