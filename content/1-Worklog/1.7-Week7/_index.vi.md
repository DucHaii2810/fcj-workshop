---
title: "Worklog Tuần 7"
date: 2026-10-26
weight: 7
chapter: false
pre: " <b> 1.7 </b> "
---
### Mục tiêu tuần 7:

- Xây dựng cơ sở tri thức pháp lý trên DynamoDB.
- Cấu hình IAM theo nguyên tắc đặc quyền tối thiểu cho Lambda.

### Các công việc cần triển khai trong tuần này:

| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | --------- | ------------ | --------------- | -------------- |
| 2 | Kiểm tra cảnh báo Budget và mức sử dụng Free Tier. Chốt Region dùng chung cho toàn bộ tài nguyên. Tạo bảng LegalArticles ở chế độ on-demand để tránh phát sinh chi phí ngoài muốn. | 26/10/2026 | 26/10/2026 | AWS Docs: DynamoDB |
| 3 | Tóm tắt nội dung các điều luật đã chọn và gắn từ khóa. Đối chiếu nội dung với văn bản chính thức. | 27/10/2026 | 27/10/2026 |  |
| 4 | Viết script seed bằng boto3 batch_writer và nạp dữ liệu. Kiểm tra lại dữ liệu bằng Explore table items. | 28/10/2026 | 28/10/2026 | AWS Docs: DynamoDB |
| 5 | Tạo IAM policy chỉ đọc bảng LegalArticles kèm quyền ghi log CloudWatch. Tạo execution role legal-ai-chat-role cho Lambda và gắn policy. | 29/10/2026 | 29/10/2026 | AWS Docs: IAM |
| 6 | Kiểm tra đọc bảng bằng AWS CLI/boto3, thử thao tác ghi để xác nhận bị từ chối. Rà soát lại quyền và bỏ những quyền không cần thiết. | 30/10/2026 | 30/10/2026 | AWS Docs: IAM |

### Kết quả đạt được tuần 7:

- Tạo bảng LegalArticles và nạp dữ liệu điều luật bằng script seed.
- Dữ liệu đã được đối chiếu với văn bản chính thức.
- Tạo IAM policy và role đặc quyền tối thiểu, xác nhận quyền ghi bị từ chối.
