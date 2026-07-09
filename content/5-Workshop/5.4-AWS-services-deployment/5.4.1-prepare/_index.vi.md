---
title : "Chuẩn bị tài nguyên"
date : 2024-01-01
weight : 1
chapter : false
pre : " <b> 5.4.1 </b> "
---

#### Tổng quan

Trước khi triển khai hệ thống SportBooking lên nền tảng AWS, thành viên trong nhóm  tiến hành chuẩn bị các tài nguyên và kiểm tra môi trường triển khai nhằm đảm bảo toàn bộ quá trình triển khai diễn ra ổn định và chính xác.

Các tài nguyên được chuẩn bị bao gồm:

- Amazon EC2
- Amazon ECR (Private Repository)
- Amazon ECS
- Amazon Aurora PostgreSQL / Amazon RDS
- Amazon ElastiCache for Redis
- Amazon S3
- AWS Secrets Manager
- Application Load Balancer
- Amazon CloudWatch

![Architecture Overview](/images/diagram_aws.jpg)

---

#### Chuẩn bị mã nguồn ứng dụng

Trước khi triển khai, thành viên trong nhóm  kiểm tra lại toàn bộ mã nguồn của hệ thống SportBooking nhằm đảm bảo ứng dụng hoạt động ổn định trong môi trường phát triển.

Các thành phần của dự án bao gồm:

- Backend API
- Frontend
- Dockerfile
- Terraform
- Tệp cấu hình môi trường (.env)

![Cấu trúc dự án ](/images/layout.jpg)

---

#### Chuẩn bị Docker Image

Ứng dụng được đóng gói dưới dạng Docker Image để thuận tiện cho việc triển khai lên Amazon ECS.

Các bước chuẩn bị gồm:

- Kiểm tra Dockerfile.
- Build Docker Image.
- Kiểm tra Docker Image sau khi build thành công.

![Docker](/images/docker/docker_file.jpg)
![Docker](/images/docker/docker_file1.jpg)
![Docker](/images/docker/docker_file_yml.jpg)
![Docker](/images/docker/docker_file_yml_1.jpg)
![Docker](/images/docker/docker_file_yml_2.jpg)
---

#### Chuẩn bị cấu hình Terraform

Trước khi triển khai hạ tầng, tôi kiểm tra các tệp cấu hình Terraform nhằm đảm bảo toàn bộ tài nguyên AWS được định nghĩa đầy đủ và chính xác.

Các tài nguyên sẽ được Terraform triển khai bao gồm:

- Hạ tầng mạng.
- Dịch vụ tính toán.
- Cơ sở dữ liệu.
- Bộ nhớ đệm.
- Lưu trữ.
- Giám sát hệ thống.

![Terraform](/images/terraform.jpg)

---

#### Kiểm tra môi trường AWS

Cuối cùng, tôi kiểm tra lại môi trường AWS trước khi bắt đầu triển khai.

Bao gồm:

- Tài khoản AWS.
- AWS CLI.
- Quyền IAM.
- Region.
- Kết nối Terraform với AWS.

Việc kiểm tra giúp đảm bảo Terraform có đầy đủ quyền để tạo và quản lý các tài nguyên trên AWS.

![AWS](/images/aws_cli.jpg)
![AWS](/images/aws_cli_sts_get_caller_identity.jpg)

---

#### Tóm tắt

Sau khi hoàn thành bước chuẩn bị, toàn bộ mã nguồn, Docker Image, cấu hình Terraform và môi trường AWS đã sẵn sàng cho quá trình triển khai các dịch vụ của hệ thống SportBooking. Ở phần tiếp theo, tôi sẽ tiến hành triển khai các dịch vụ AWS và cấu hình hạ tầng theo kiến trúc đã thiết kế.