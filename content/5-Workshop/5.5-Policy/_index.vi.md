---
title : "Cấu hình Security Policies"
date : 08-07-2026
weight : 5
chapter : false
pre : " <b> 5.5 </b> "
---

#### Tổng quan

Trong phần này, tôi tiến hành cấu hình các chính sách bảo mật (Security Policies) cho hệ thống SportBooking nhằm kiểm soát quyền truy cập giữa các dịch vụ AWS. Việc áp dụng các chính sách phù hợp giúp đảm bảo chỉ những tài nguyên được cấp quyền mới có thể truy cập vào các dịch vụ của hệ thống, góp phần tăng cường tính bảo mật và giảm thiểu các rủi ro trong quá trình vận hành.

---

#### Cấu hình IAM Role cho Amazon ECS

+ Tạo IAM Role dành cho Amazon ECS Task.
+ Gán các quyền cần thiết để ứng dụng có thể truy cập Amazon ECR, Amazon CloudWatch và AWS Secrets Manager.

![IAM Role](/images/cloud/IAM/IAM_ROLE.jpg)

---

---

#### Cấu hình AWS Secrets Manager

+ Tạo Secret để lưu trữ các thông tin nhạy cảm của hệ thống.
+ Cấp quyền cho Amazon ECS truy cập Secret thông qua IAM Role.


---

#### Cấu hình Security Group

+ Kiểm soát lưu lượng truy cập giữa Application Load Balancer, Amazon ECS, Amazon RDS và Amazon ElastiCache.
+ Chỉ cho phép các cổng dịch vụ cần thiết.

![Security Group](/images/cloud/VPC/security_group.jpg)

---

#### Kiểm tra Security Policies

+ Kiểm tra IAM Role đã được gán cho Amazon ECS.
+ Kiểm tra ứng dụng có thể truy cập AWS Secrets Manager.
+ Kiểm tra các Security Group hoạt động đúng theo cấu hình.


---

#### Tóm tắt

Sau khi hoàn thành các bước trên, hệ thống SportBooking đã được cấu hình các chính sách bảo mật phù hợp. Các dịch vụ AWS chỉ cho phép truy cập theo đúng quyền đã được cấp, đảm bảo tính bảo mật và an toàn cho hệ thống trong quá trình triển khai và vận hành.