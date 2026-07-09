---
title: "Workshop"
date: 08-07-2026
weight: 5
chapter: false
pre: " <b> 5. </b> "
---

{{% notice warning %}}
⚠️ **Lưu ý:** Các thông tin dưới đây chỉ nhằm mục đích tham khảo, vui lòng **không sao chép nguyên văn** cho bài báo cáo của bạn kể cả warning này.
{{% /notice %}}

# Triển khai hạ tầng AWS cho hệ thống SportBooking

#### Tổng quan

Trong chương này, tôi tiến hành triển khai hạ tầng Cloud cho hệ thống **SportBooking** trên nền tảng **Amazon Web Services (AWS)**. Toàn bộ hạ tầng được xây dựng theo phương pháp **Infrastructure as Code (IaC)** bằng **Terraform**, giúp tự động hóa quá trình tạo và quản lý tài nguyên, đồng thời đảm bảo tính nhất quán, khả năng mở rộng và thuận tiện trong quá trình vận hành hệ thống.

Trong quá trình triển khai, tôi lần lượt xây dựng hạ tầng mạng, triển khai các dịch vụ AWS, kiểm tra trạng thái hoạt động của từng dịch vụ, xác minh khả năng vận hành của ứng dụng và cấu hình các chính sách bảo mật nhằm đảm bảo hệ thống hoạt động ổn định trên môi trường Cloud.

Các dịch vụ AWS được sử dụng trong dự án gồm:

+ **Amazon VPC** – Xây dựng mạng riêng cho hệ thống, bao gồm Public Subnet, Private Subnet, Internet Gateway, NAT Gateway, Route Table và Security Group.
+ **Amazon EC2** – Cung cấp máy chủ ảo phục vụ cho việc kiểm thử và quản trị hệ thống.
+ **Amazon Elastic Container Registry (Amazon ECR)** – Lưu trữ Docker Image của ứng dụng trước khi triển khai.
+ **Amazon Elastic Container Service (Amazon ECS)** – Triển khai và quản lý các Docker Container của ứng dụng.
+ **Amazon RDS PostgreSQL** – Cung cấp cơ sở dữ liệu quan hệ được quản lý bởi AWS.
+ **Amazon ElastiCache for Redis** – Triển khai bộ nhớ đệm giúp tăng tốc độ truy xuất dữ liệu.
+ **Amazon S3** – Lưu trữ hình ảnh và các tệp của hệ thống.
+ **AWS Secrets Manager** – Quản lý tập trung các thông tin nhạy cảm như mật khẩu và chuỗi kết nối.
+ **Application Load Balancer (ALB)** – Phân phối lưu lượng truy cập đến các dịch vụ đang hoạt động.
+ **Amazon CloudWatch** – Giám sát tài nguyên và thu thập nhật ký hệ thống.
+ **Amazon SNS** – Gửi thông báo khi hệ thống phát sinh sự kiện hoặc cảnh báo.

Sau khi hoàn thành chương này, toàn bộ hạ tầng và ứng dụng **SportBooking** được triển khai thành công trên AWS Cloud, sẵn sàng cho quá trình kiểm thử, vận hành và đánh giá. Cuối cùng, các tài nguyên AWS sẽ được dọn dẹp nhằm tránh phát sinh chi phí  sau khi hoàn tất quá trình triển khai tầm khoảng từ 100 - 200$  .

#### Nội dung

1. [Tổng quan về workshop](5.1-Workshop-overview/)
2. [Chuẩn bị](5.2-Prerequiste/)
3. [Triển khai hạ tầng mạng AWS](5.3-vpc/)
4. [Triển khai các dịch vụ AWS](5.4-AWS-service-deployment/)
5. [Cấu hình Security Policies](5.5-Policy/)
6. [Dọn dẹp tài nguyên](5.6-Cleanup/)