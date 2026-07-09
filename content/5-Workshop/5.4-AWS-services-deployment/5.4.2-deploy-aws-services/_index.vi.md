---
title : "Triển khai các dịch vụ AWS"
date : 08-07-2026
weight : 2
chapter : false
pre : " <b> 5.4.2 </b> "
---

Trong phần này, thành viên trong nhóm  tiến hành triển khai các dịch vụ AWS phục vụ cho hệ thống SportBooking. Các dịch vụ được cấu hình theo kiến trúc đã thiết kế nhằm đáp ứng nhu cầu triển khai ứng dụng, lưu trữ dữ liệu, quản lý container và giám sát hệ thống.

1. Truy cập **AWS Management Console** và lần lượt mở các dịch vụ cần triển khai.

2. Triển khai **Amazon ECR (Elastic Container Registry)**.

+ Tạo một **Private Repository** để lưu trữ Docker Image của ứng dụng.
+ Sau khi tạo thành công, tiến hành xác thực Docker với Amazon ECR và đẩy Docker Image lên Repository.

![Amazon ECR (Elastic Container Registry)](/images/cloud/ECR/ECR.jpg)
![Amazon ECR (Elastic Container Registry)](/images/cloud/ECR/Private_repo.jpg)
![Amazon ECR (Elastic Container Registry)](/images/cloud/ECR/success.jpg)
---

3. Triển khai **Amazon ECS (Elastic Container Service)**.

+ Tạo **Amazon ECS Cluster** để quản lý các container của hệ thống.
+ Tạo **Health Check** kiểm tra trạng thái .
+ Tạo **ECS Service** và liên kết với Cluster để triển khai ứng dụng.


![Amazon ECS (Elastic Container Service) - Clusters](/images/cloud/ECS/Clusters.jpg)
![Amazon ECS (Elastic Container Service) - Clusters](/images/cloud/ECS/test_Cluster.jpg)

![Amazon ECS (Elastic Container Service) - Services -   Health](/images/cloud/ECS/Health.jpg)

![Amazon ECS (Elastic Container Service) - Services](/images/cloud/ECS/Services.jpg)
![Amazon ECS (Elastic Container Service) - Services](/images/cloud/ECS/Services_succ.jpg)
---

4. Triển khai **Amazon Aurora SQL Server / Amazon RDS**.

+ Tạo cơ sở dữ liệu SQL Server.
+ Cấu hình thông tin kết nối và Security Group.
+ Kiểm tra trạng thái của cơ sở dữ liệu sau khi tạo thành công.

![RDS](/images/cloud/RDS/RDS.jpg)
![DATABASE](/images/cloud/RDS/Database.jpg)

---

5. Triển khai **Amazon ElastiCache for Redis**.

+ Tạo Redis OSS Cache.
+ Cấu hình mạng và Security Group.
+ Kiểm tra Endpoint sau khi Redis được khởi tạo.

![REDIS](/images/cloud/Redis/Overview.jpg)
![REDIS](/images/cloud/Redis/Redis_success.jpg)
![REDIS](/images/cloud/Redis/Redis.jpg)

---


6. Triển khai **Amazon ElastiCache for Redis**.

+ Tạo Redis OSS Cache trên Amazon ElastiCache.
+ Cấu hình Cache Cluster, VPC và Subnet Group.
+ Cấu hình Security Group cho phép Amazon ECS kết nối đến Redis.
+ Hoàn tất triển khai và kiểm tra trạng thái **Available**.

![ElastiCache](/images/cloud/ElastiCache/ElastiCache.jpg)
![ElastiCache](/images/cloud/ElastiCache/ElastiCache_success.jpg)

---

7. Triển khai **Application Load Balancer**.

+ Tạo Target Group.
+ Tạo Application Load Balancer.
+ Liên kết Load Balancer với Amazon ECS Service để phân phối lưu lượng truy cập đến các container.

![ALB (Application Load Balancer) ](/images/cloud/ALB/alb.jpg)

---
8. Triển khai **Amazon EC2**.

+ Tạo Amazon EC2 Instance phục vụ cho việc kiểm thử và quản trị hệ thống.
+ Cấu hình VPC, Subnet và Security Group cho EC2.
+ Kiểm tra trạng thái hoạt động của EC2 sau khi khởi tạo.

![EC2](/images/cloud/EC2/Overview.jpg)
![EC2](/images/cloud/EC2/Load_Balances.jpg)
![EC2](/images/cloud/EC2/Load_Balances1.jpg)
![EC2](/images/cloud/EC2/Target_group.jpg)
![EC2](/images/cloud/EC2/EC2.jpg)

---

9. Triển khai **AWS Secrets Manager**

+ Tạo Secret để lưu trữ các thông tin nhạy cảm của hệ thống.
+ Cấp quyền cho Amazon ECS truy cập Secret thông qua IAM Role.


---

Sau khi hoàn thành các bước trên, toàn bộ các dịch vụ AWS đã được triển khai thành công và sẵn sàng phục vụ cho việc vận hành hệ thống SportBooking trên nền tảng AWS Cloud. Phần tiếp theo sẽ tiến hành kiểm tra trạng thái hoạt động của các dịch vụ và xác nhận quá trình triển khai thành công.