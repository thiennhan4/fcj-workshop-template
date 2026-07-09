---
title : "Kiểm tra các dịch vụ AWS"
date : 08-07-2026
weight : 3
chapter : false
pre : " <b> 5.4.3 </b> "
---

Trong phần này, thành viên trong nhóm tiến hành kiểm tra trạng thái hoạt động của các dịch vụ AWS sau khi triển khai nhằm đảm bảo toàn bộ hạ tầng đã được cấu hình chính xác và sẵn sàng phục vụ cho hệ thống SportBooking.

#### Kiểm tra Amazon EC2

+ Kiểm tra trạng thái của EC2 Instance.
+ Đảm bảo EC2 ở trạng thái **Running**.

![EC2](/images/cloud/EC2/EC2.jpg)

---

#### Kiểm tra Amazon ECR

+ Kiểm tra Docker Image đã được đẩy thành công lên Private Repository.
+ Xác nhận Repository hoạt động bình thường.

![Amazon ECR (Elastic Container Registry)](/images/cloud/ECR/ECR.jpg)

---

#### Kiểm tra Amazon ECS

+ Kiểm tra trạng thái của ECS Cluster.
+ Kiểm tra ECS Service đang ở trạng thái **Active**.
+ Kiểm tra Health Status của ứng dụng.

![Amazon ECS (Elastic Container Service) - Clusters](/images/cloud/ECS/Clusters.jpg)
![Amazon ECS (Elastic Container Service) - Services](/images/cloud/ECS/Services.jpg)
![Amazon ECS (Elastic Container Service) - Services -   Health](/images/cloud/ECS/Health.jpg)

---

#### Kiểm tra Amazon Aurora SQL Server / Amazon RDS

+ Kiểm tra trạng thái của cơ sở dữ liệu.
+ Đảm bảo Database ở trạng thái **Available**.

![RDS](/images/cloud/RDS/RDS.jpg)
![DATABASE](/images/cloud/RDS/Database.jpg)
---

#### Kiểm tra Amazon ElastiCache for Redis

+ Kiểm tra trạng thái của Redis OSS Cache.
+ Đảm bảo Redis ở trạng thái **Available**.

![REDIS](/images/cloud/Redis/Redis.jpg)

---

#### Kiểm tra Application Load Balancer

+ Kiểm tra trạng thái của Target Group.
+ Kiểm tra Health Check của Application Load Balancer.
+ Đảm bảo các Target ở trạng thái **Healthy**.

![ALB (Application Load Balancer) ](/images/cloud/ALB/alb.jpg)

---
