---
title : "Giới thiệu tổng quan"
date : 06/07/2026
weight : 1
chapter : false
pre : " <b> 5.1. </b> "
---

#### Giới thiệu dự án SportBooking

Hệ thống **SportBooking** được thiết kế nhằm cung cấp nền tảng quản lý và đặt sân thể thao trực tuyến ổn định, bảo mật và có khả năng mở rộng linh hoạt. Toàn bộ hạ tầng của hệ thống được tự động hóa triển khai trên nền tảng điện toán đám mây **AWS (Amazon Web Services)** thông qua công cụ Infrastructure as Code (IaC) **Terraform**, đảm bảo tính nhất quán và dễ dàng quản lý.

#### Sơ đồ kiến trúc hệ thống (Architecture Diagram)

Dưới đây là mô hình kiến trúc hạ tầng tổng thể của dự án SportBooking được triển khai trên AWS:

![AWS Architecture Overview](/images/diagram_aws.jpg)

#### Các thành phần chính trong kiến trúc đám mây

Kiến trúc hệ thống được chia làm 3 phân vùng chính để tối ưu hiệu năng và bảo mật:

1. **Edge Layer (Tầng biên):**
   * **Amazon Route 53 & AWS WAF:** Điều hướng tên miền và ngăn chặn các cuộc tấn công mạng nguy hiểm (SQL Injection, DDoS).
   * **Amazon CloudFront:** Mạng lưới phân phối nội dung (CDN) giúp tăng tốc độ tải trang Front-end tĩnh được lưu trữ tại **Amazon S3 Frontend**.
   * **AWS Certificate Manager (ACM):** Quản lý và cấp phát chứng chỉ SSL/TLS mã hóa lưu lượng truy cập.

2. **Network & Compute Layer (Tầng mạng & Tính toán):**
   * **VPC (Virtual Private Cloud):** Thiết lập mạng ảo độc lập phân chia rõ ràng giữa **Public Subnet** (chứa ALB, NAT Gateway) và **Private Subnet** (chứa logic ứng dụng).
   * **AWS Fargate (Amazon ECS):** Chạy ứng dụng backend **.NET 9** dưới dạng các Container (Docker) phân bổ đều trên 2 vùng sẵn sàng khác nhau (**Multi-AZ: Availability Zone A & B**) để đảm bảo tính sẵn sàng cao (High Availability).
   * **Application Load Balancer (ALB):** Tiếp nhận traffic từ CloudFront và cân bằng tải thông minh đến các ECS Tasks đang hoạt động khỏe mạnh (Healthy).

3. **Data & Management Layer (Tầng dữ liệu & Quản trị):**
   * **Amazon RDS & Amazon ElastiCache (Redis):** Hệ thống cơ sở dữ liệu chính (Primary/Standby DB) kết hợp bộ nhớ đệm cache tốc độ cao nằm hoàn toàn trong vùng mạng cô lập (Private Data Subnet).
   * **Amazon ECR & AWS Secrets Manager:** Lưu trữ bảo mật các Docker Images và quản lý tập trung các thông tin nhạy cảm (Connection String, Key).
   * **Monitoring Group (CloudWatch & Amazon SNS):** Giám sát trạng thái hệ thống, tài nguyên và tự động gửi thông báo qua Email khi có sự cố phát sinh.

---

#### Quy trình triển khai và Xác thực hệ thống (Verification & API Testing)

Dự án đã được đóng gói và kiểm thử thành công qua chuỗi quy trình chuẩn CI/CD thủ công:

* **Khởi tạo hạ tầng:** Cấu hình AWS Profile và dùng **Terraform** để khởi tạo, cấp phát thành công 35 tài nguyên đám mây tự động.
* **Đóng gói & Phát hành:** Mã nguồn backend `.NET 9` được đóng gói thành Docker Image, push lên kho lưu trữ **Amazon ECR** khu vực Singapore và deploy lên cluster **ECS Fargate**.
* **Kiểm tra trạng thái (Health Check):** Hệ thống Load Balancer (ALB Target Group) xác nhận dịch vụ hoạt động ổn định và API phản hồi trạng thái `/health = ok`.

##### Kết quả kiểm thử API qua Postman

Các tính năng cốt lõi của API Backend đã được xác thực hoạt động chính xác với dữ liệu thực tế từ môi trường Cloud:

1. **Tính năng Xác thực (Authentication):**
   * **Đăng ký tài khoản (`POST /api/auth/register`):** Hệ thống xử lý cấp tài khoản mới và trả về chuỗi mã hóa định danh JWT Token thành công (`200 OK`).
   * **Ràng buộc dữ liệu:** Xử lý ngoại lệ chính xác khi đăng ký trùng tên hệ thống tự động phản hồi mã `409 Conflict` kèm thông báo *"Username đã tồn tại"*.
   * **Đăng nhập (`POST /api/auth/login`):** Xác thực người dùng và cấp quyền truy cập hợp lệ.

2. **Tính năng Nghiệp vụ (`GET /api/venues`):**
   * API truy vấn thành công danh sách các khu tổ hợp thể thao (ví dụ: *Khu Thể Thao Bách Khoa - Sân bóng xịn xò*) từ cơ sở dữ liệu Cloud RDS và trả về định dạng JSON hoàn chỉnh.

![overview](/images/test_api.jpg)
