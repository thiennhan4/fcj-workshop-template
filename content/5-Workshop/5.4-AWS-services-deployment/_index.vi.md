---
title : "Triển khai các dịch vụ AWS"
date : 08-07-2026
weight : 4
chapter : false
pre : " <b> 5.4. </b> "
---

#### Tổng quan

Trong phần này, tôi tiến hành triển khai các dịch vụ AWS phục vụ cho hệ thống **SportBooking** dựa trên kiến trúc hạ tầng đã được xây dựng ở phần trước. Mục tiêu của bước này là triển khai các dịch vụ tính toán, lưu trữ, cơ sở dữ liệu và giám sát nhằm đảm bảo hệ thống có thể hoạt động ổn định trên nền tảng AWS Cloud.

Các dịch vụ được triển khai bao gồm:

- Amazon EC2
- Amazon Elastic Container Registry (Amazon ECR)
- Amazon Elastic Container Service (Amazon ECS)
- Amazon Aurora PostgreSQL / Amazon RDS
- Amazon ElastiCache for Redis
- Amazon S3
- AWS Secrets Manager
- Application Load Balancer (ALB)
- Amazon CloudWatch
...

Việc kết hợp các dịch vụ trên giúp xây dựng một kiến trúc hiện đại, có khả năng mở rộng, tăng tính sẵn sàng, đồng thời đảm bảo tính bảo mật và hiệu năng cho hệ thống SportBooking trong quá trình vận hành.

![Architecture Overview](/images/diagram_aws.jpg)

#### Nội dung

- [Chuẩn bị tài nguyên](4.1-prepare-resources/)
- [Triển khai các dịch vụ AWS](4.2-deploy-aws-services/)
- [Kiểm tra các dịch vụ AWS](4.3-verify-aws-services/)
- [Kiểm tra triển khai ứng dụng](4.4-validate-application-deployment/)