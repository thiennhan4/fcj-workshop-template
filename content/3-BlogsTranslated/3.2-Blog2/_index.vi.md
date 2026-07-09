---
title: "Blog 2"
date: 08-07-2026
weight: 2
chapter: false
pre: " <b> 3.2. </b> "
---


# BẢO MẬT .NET MICROSERVICES TRÊN AWS VỚI MICROSOFT ENTRA ID

Trong quá trình tìm hiểu về kiến trúc Microservices trên AWS, mình đọc được bài viết **"Securing .NET Microservices with Entra ID on AWS"** trên AWS .NET Blog. Điều mình thấy ấn tượng là AWS hướng dẫn cách kết hợp **Microsoft Entra ID (Azure AD)** với **OAuth 2.0 Client Credentials Flow** để xây dựng cơ chế xác thực và phân quyền an toàn giữa các microservice chạy trên AWS.

---

## 1. Bài toán

Trong kiến trúc Microservices, các service thường xuyên giao tiếp với nhau. Ví dụ:

- Order Service gọi Inventory Service để kiểm tra tồn kho.
- Inventory Service tiếp tục gọi Pricing Service để tính giá sản phẩm.

Nếu không có cơ chế xác thực phù hợp, các service có thể truy cập lẫn nhau mà không được kiểm soát, làm tăng nguy cơ truy cập trái phép hoặc rò rỉ dữ liệu.

---

## 2. Giải pháp của AWS

AWS đề xuất đăng ký mỗi microservice như một **Application** trong Microsoft Entra ID. Mỗi service sẽ có:

- Client ID
- Client Secret
- Scope (quyền truy cập) riêng

Khi **Service A** cần gọi **Service B**, quy trình sẽ diễn ra như sau:

1. Service A gửi Client ID và Client Secret đến Microsoft Entra ID.
2. Entra ID xác thực và cấp một **Access Token**.
3. Service A gửi request đến Service B kèm Access Token trong `Authorization: Bearer`.
4. Service B xác minh Access Token trước khi xử lý request.

Nhờ đó, chỉ những service được cấp quyền mới có thể truy cập API của nhau.

---

## 3. Một số điểm nổi bật

Bài viết cũng đề cập đến nhiều thực hành tốt giúp hệ thống hoạt động hiệu quả hơn:

- Sử dụng **OAuth 2.0 Client Credentials Flow** cho giao tiếp giữa các service.
- Lưu **Client Secret** trong **AWS Secrets Manager** thay vì hard-code trong ứng dụng.
- Cache **Access Token** để tái sử dụng cho đến khi gần hết hạn, giúp giảm số lần yêu cầu token mới và cải thiện hiệu năng.
- Sử dụng `[Authorize]` trong ASP.NET Core để tự động bảo vệ các API khỏi các request không hợp lệ.

---

## 4. Đánh giá theo AWS Well-Architected Framework

### Security

- Mỗi microservice có danh tính và quyền truy cập riêng.
- Chỉ những service được cấp quyền mới có thể truy cập API.

### Operational Excellence

- Secrets được quản lý tập trung bằng AWS Secrets Manager.
- Dễ dàng thay đổi hoặc xoay vòng thông tin xác thực.

### Reliability

- Access Token được kiểm tra và tự động làm mới khi gần hết hạn.
- Đảm bảo quá trình xác thực luôn ổn định.

### Performance Efficiency

- Cache Access Token giúp giảm độ trễ.
- Hạn chế số lần yêu cầu token đến Microsoft Entra ID.

### Cost Optimization

- Giảm số lần xác thực không cần thiết.
- Tận dụng các dịch vụ managed của AWS để giảm chi phí vận hành.

---

## 5. Kết luận

Theo mình, đây là một giải pháp phù hợp cho các hệ thống **.NET Microservices** chạy trên AWS nhưng sử dụng **Microsoft Entra ID** để quản lý danh tính. Việc áp dụng **OAuth 2.0 Client Credentials Flow** không chỉ giúp bảo vệ giao tiếp giữa các service mà còn giúp hệ thống dễ mở rộng, dễ quản lý và tuân theo các thực hành bảo mật hiện đại.

---

## 6. Link bài viết gốc

https://aws.amazon.com/blogs/dotnet/securing-net-microservices-with-entra-id-on-aws/

---

## 7. Hướng dẫn

- Đọc bài viết gốc để hiểu rõ hơn về kiến trúc xác thực giữa các microservice.
- Tìm hiểu thêm về OAuth 2.0 Client Credentials Flow và Microsoft Entra ID.
- Thực hành triển khai các .NET Microservices trên Amazon ECS hoặc AWS Fargate kết hợp AWS Secrets Manager để quản lý thông tin xác thực.