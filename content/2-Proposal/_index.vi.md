---
title: "Bản đề xuất"
date: 2026-11-19
weight: 2
chapter: false
pre: " <b> 2. </b> "
---
# Legal RAG Platform: Hệ thống Tư vấn Pháp lý Tự động cho Nghị định 13/2023/NĐ-CP
## Giải pháp AWS Serverless Hợp nhất tích hợp LLM cho Tra cứu và Phân tích Pháp lý Thời gian thực

### 1. Tóm tắt điều hành
Legal RAG Platform là hệ thống tư vấn tự động giúp người dùng và thành viên nhóm tra cứu nhanh và phân tích các quy định pháp luật Việt Nam phức tạp. Hệ thống tập trung vào Nghị định 13/2023/NĐ-CP về bảo vệ dữ liệu cá nhân. Nền tảng được xây dựng trên kiến trúc serverless hoàn toàn trên AWS và sử dụng mô hình ngôn ngữ lớn (LLM) từ Groq API (`qwen/qwen3.8-27b`). Câu trả lời bám sát văn bản pháp luật thực tế, giúp giảm nguy cơ AI bịa thông tin (hallucination). Nền tảng cũng giữ chi phí vận hành ở mức $0 nhờ nằm trong hạn mức AWS Free Tier.

### 2. Đặt vấn đề
### Vấn đề
- Các văn bản pháp luật như Nghị định 13/2023/NĐ-CP dài, dày đặc và khó tra cứu thủ công đối với người không chuyên.
- Các công cụ AI đa năng, chẳng hạn như bản miễn phí của ChatGPT, thường thiếu hiểu biết chuyên sâu về pháp luật Việt Nam. Chúng có xu hướng đưa ra câu trả lời chung chung mà không có căn cứ pháp lý chính xác.
- Tự xây dựng hệ thống AI trên hạ tầng riêng tốn kém phần cứng và phức tạp khi vận hành.

### Giải pháp
Nền tảng sử dụng quy trình RAG (Retrieval-Augmented Generation) tự động. Khi người dùng gửi câu hỏi, hệ thống tìm kiếm trong cơ sở dữ liệu các điều khoản pháp luật liên quan nhất và đưa chúng vào System Prompt. Sau đó, LLM tạo câu trả lời trích dẫn rõ ràng các điều khoản đó.
- Amazon DynamoDB lưu trữ các điều khoản pháp luật đã trích xuất trong bảng `LegalArticles`.
- AWS Lambda xử lý logic backend, và Amazon API Gateway cung cấp một endpoint API ổn định.
- Groq API với mô hình `qwen/qwen3.8-27b` tạo ra câu trả lời rõ ràng, mạch lạc.
- Amazon S3 Static Website lưu trữ giao diện web, nơi người dùng tương tác thông qua khung chat.

### Lợi ích và Hiệu quả đầu tư (ROI)
- Độ chính xác cao: Câu trả lời bám sát văn bản pháp luật được cung cấp, minh bạch và có căn cứ rõ ràng.
- Tối ưu chi phí: Thiết kế serverless chạy trong gói AWS Free Tier, với chi phí hàng tháng gần như $0.
- Khả năng mở rộng: Kiến trúc tách rời giúp dễ dàng thêm các văn bản pháp luật mới, chẳng hạn như Luật An toàn thông tin mạng hoặc Luật Công nghệ thông tin, vào DynamoDB trong tương lai.

### 3. Kiến trúc giải pháp
Hệ thống tuân theo kiến trúc serverless kết nối frontend, backend và LLM bên ngoài thành một vòng khép kín.

### Các dịch vụ và công nghệ AWS
- **Amazon S3 Static Website**: Lưu trữ và phân phối giao diện web tĩnh (`index.html`, CSS và JavaScript).
- **Amazon API Gateway**: Cung cấp HTTP/REST API công khai, xử lý CORS và chuyển tiếp request từ client đến Lambda.
- **AWS Lambda (Python)**: Chạy logic RAG, truy vấn DynamoDB và gọi Groq API.
- **Amazon DynamoDB (`LegalArticles`)**: Lưu trữ các điều khoản pháp luật và hỗ trợ tra cứu nhanh theo từ khóa.
- **Groq API (`qwen/qwen3.8-27b`)**: Tạo và phân tích ngôn ngữ tự nhiên dựa trên ngữ cảnh pháp lý được cung cấp.

### Thiết kế thành phần
- **Frontend**: Người dùng mở website lưu trữ trên S3 và nhập câu hỏi vào khung chat. Trình duyệt gửi HTTP POST request chứa câu hỏi qua HTTPS tới API Gateway.
- **API Gateway**: Tiếp nhận request, kiểm tra cấu hình CORS và chuyển tiếp payload tới hàm Lambda.
- **Truy xuất dữ liệu (DynamoDB)**: Hàm `retrieve_legal_context` tìm kiếm trong bảng `LegalArticles` các điều khoản liên quan. Ví dụ, nó có thể truy xuất quy định về xử lý vi phạm liên quan đến căn cước công dân (CCCD) và dữ liệu cá nhân theo Nghị định 13.
- **Tăng cường và Tạo sinh (Groq API)**: Lambda kết hợp câu hỏi của người dùng với ngữ cảnh pháp lý đã truy xuất thành một System Prompt với các ràng buộc chặt chẽ, yêu cầu câu trả lời chỉ dựa trên ngữ cảnh được cung cấp. Sau đó nó gọi Groq API.
- **Luồng phản hồi**: Groq trả kết quả về cho Lambda. Lambda định dạng JSON response chuẩn và gửi ngược qua API Gateway để hiển thị trên khung chat.

### 4. Triển khai kỹ thuật
**Các giai đoạn triển khai**
- Giai đoạn 1, Thiết kế Prompt và Cơ chế RAG: Viết System Prompt xác định vai trò chuyên gia pháp lý và đặt ràng buộc ngữ cảnh cấm bịa thông tin.
- Giai đoạn 2, Backend và Database:
  - Tạo bảng DynamoDB `LegalArticles`.
  - Viết code Python cho AWS Lambda, bao gồm hàm truy xuất và tích hợp Groq API.
  - Cấu hình API Gateway, bật header CORS và triển khai xử lý lỗi chuẩn hóa. Bao gồm mã 400 và 502/504, cũng như mã 429 khi vượt giới hạn tần suất (rate limit) của Groq API.
- Giai đoạn 3, Kiểm thử và Tinh chỉnh: Gửi HTTP POST request bằng `curl` và kiểm thử trực tiếp trên giao diện web. Theo dõi log trên Amazon CloudWatch.

### 5. Lộ trình & Các cột mốc
**Lộ trình dự án**
- Nghiên cứu và Thiết kế: Xác định phạm vi pháp lý (Nghị định 13/2023/NĐ-CP) và thiết kế luồng dữ liệu RAG.
- Phát triển và Triển khai: Xây dựng database DynamoDB, hoàn thiện hàm Lambda và cấu hình API Gateway.
- Tích hợp và Kiểm thử: Kết nối website tĩnh S3 với API Gateway, kiểm thử độ chính xác câu trả lời từ Groq LLM và tinh chỉnh xử lý lỗi.

### 6. Ước tính ngân sách
### Chi phí hạ tầng
- Dịch vụ AWS:
  - Amazon S3: Miễn phí trong giới hạn Free Tier.
  - Amazon API Gateway: Miễn phí cho 1 triệu request đầu tiên mỗi tháng.
  - AWS Lambda: Miễn phí tối đa 1 triệu request mỗi tháng.
  - Amazon DynamoDB: Miễn phí trong giới hạn 25 GB lưu trữ và 25 WCU cùng 25 RCU.
  Tổng chi phí AWS: $0.00 mỗi tháng.
- Groq API:
  Dự án sử dụng gói miễn phí cho mô hình mã nguồn mở (`qwen/qwen3.8-27b`).

Tổng đầu tư dự án: 0 VNĐ ($0).

### 7. Đánh giá rủi ro
#### Ma trận rủi ro
- Quá tải API (giới hạn tần suất Groq API, lỗi 429): Triển khai xử lý lỗi và hiển thị thông báo rõ ràng, thân thiện trên giao diện chat khi tạm thời vượt giới hạn request.
- Câu trả lời AI không chính xác (hallucination): Tăng cường System Prompt để mô hình chỉ sử dụng ngữ cảnh pháp lý truy xuất từ DynamoDB và không suy diễn vượt ngoài nguồn đó.
- Lỗi CORS trên trình duyệt: Cấu hình đầy đủ header CORS (`Access-Control-Allow-Origin: *`, `POST`, `OPTIONS`) trực tiếp trên API Gateway.

### 8. Kết quả kỳ vọng
#### Thành tựu kỹ thuật:
Một backend serverless hoàn chỉnh, tự động mở rộng, vận hành ổn định và hoạt động với chi phí $0.
#### Giá trị thực tiễn:
Một API gateway chuẩn hóa và giao diện chat trực quan cho phép tra cứu nhanh, chính xác các quy định cốt lõi của Nghị định 13/2023/NĐ-CP. Nền tảng phục vụ tốt cho cả học tập và nghiên cứu.