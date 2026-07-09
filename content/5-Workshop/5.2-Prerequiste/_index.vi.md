---
title : "Các bước chuẩn bị"
date : 08-07-2026
weight : 2
chapter : false
pre : " <b> 5.2. </b> "
---

#### Chuẩn bị môi trường phát triển

Trước khi triển khai hệ thống SportBooking lên AWS Cloud, thành viên trong nhóm  tiến hành chuẩn bị môi trường phát triển và cài đặt các công cụ cần thiết để phục vụ cho quá trình xây dựng hạ tầng, triển khai ứng dụng và quản lý tài nguyên trên nền tảng AWS.

Các công cụ được sử dụng trong quá trình thực hiện gồm:

- Visual Studio Code
- Git
- Docker Desktop
- Terraform
- AWS CLI
- Tài khoản AWS

*Chèn hình ảnh cài đặt hoặc các công cụ sử dụng tại đây.*

---

#### Cấu hình AWS CLI

Sau khi cài đặt AWS CLI, tôi tiến hành cấu hình tài khoản AWS để Terraform và các công cụ khác có thể xác thực và làm việc với các dịch vụ trên AWS.

Thực hiện cấu hình bằng lệnh:

```bash
aws configure
```

Sau đó nhập các thông tin:

- AWS Access Key ID
- AWS Secret Access Key
- Default Region
- Default Output Format

Để kiểm tra việc cấu hình đã thành công, thành viên trong nhóm  sử dụng lệnh:

```bash
aws sts get-caller-identity
```

Lệnh trên giúp xác nhận AWS CLI đã kết nối thành công tới tài khoản AWS và sẵn sàng cho quá trình triển khai.

![aws_cli](/images/aws_cli.jpg)
![aws_cli_sts_get_caller_identity](/images/aws_cli_sts_get_caller_identity.jpg)
---

#### Chuẩn bị Terraform

Để triển khai hạ tầng theo mô hình **Infrastructure as Code (IaC)**, tôi sử dụng Terraform để xây dựng toàn bộ kiến trúc AWS cho hệ thống SportBooking.

Các Terraform script được tổ chức thành nhiều file và module nhằm thuận tiện cho việc quản lý, mở rộng và bảo trì hệ thống trong quá trình phát triển.

Sau khi hoàn thành các file cấu hình Terraform, tôi tiến hành khởi tạo môi trường làm việc bằng lệnh:

```bash
terraform init
```

Tiếp theo, thành viên trong nhóm  kiểm tra tính hợp lệ của các file cấu hình:

```bash
terraform validate
```

Sau đó xem trước kế hoạch triển khai các tài nguyên trên AWS:

```bash
terraform plan
```

Khi toàn bộ cấu hình hợp lệ, thành viên trong nhóm  triển khai hạ tầng bằng lệnh:

```bash
terraform apply
```

Quá trình này tự động tạo toàn bộ các tài nguyên AWS theo kiến trúc đã thiết kế.



![terraform](/images/terraform.jpg)

---

#### Kiểm tra tài nguyên trên AWS Console

Sau khi Terraform triển khai thành công, thành viên trong nhóm  tiến hành kiểm tra toàn bộ tài nguyên trên AWS Console để đảm bảo hạ tầng đã được tạo chính xác và sẵn sàng cho việc triển khai ứng dụng.

Các tài nguyên được kiểm tra bao gồm:

- Amazon VPC
- Public Subnet và Private Subnet
- Internet Gateway và NAT Gateway
- Route Tables
- Security Groups
- Application Load Balancer
- Amazon ECS Cluster
- Amazon ECS Service
- Amazon ECR Repository
- Amazon RDS PostgreSQL
- Amazon ElastiCache Redis
- Amazon S3 Bucket
- AWS Secrets Manager
- Amazon CloudWatch
- Amazon SNS

Việc kiểm tra giúp xác nhận toàn bộ tài nguyên đã được tạo đúng theo kiến trúc hệ thống và đảm bảo môi trường triển khai đã sẵn sàng cho bước triển khai ứng dụng SportBooking lên AWS Cloud.
![cloud](/images/cloud/ECS/ECS.jpg)
![cloud](/images/cloud/EC2/EC2.jpg)
![cloud](/images/cloud//ECR/ECR.jpg)


