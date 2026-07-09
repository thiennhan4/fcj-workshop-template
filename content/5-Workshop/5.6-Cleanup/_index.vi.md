---
title : "Dọn dẹp tài nguyên"
date : 2024-01-01
weight : 6
chapter : false
pre : " <b> 5.6. </b> "
---

#### Dọn dẹp tài nguyên

Sau khi hoàn thành quá trình triển khai và kiểm thử hệ thống **SportBooking**, tôi tiến hành xóa các tài nguyên AWS đã sử dụng nhằm tránh phát sinh chi phí không cần thiết và đảm bảo môi trường AWS được dọn dẹp sau khi kết thúc quá trình thực hành.

Trong quá trình này, các dịch vụ được xóa theo thứ tự phù hợp để tránh xảy ra lỗi phụ thuộc giữa các tài nguyên.

---

#### Dọn dẹp

1. Xóa **Amazon ECS Service**.

+ Truy cập **Amazon ECS**.
+ Chọn Cluster của hệ thống SportBooking.
+ Dừng và xóa ECS Service đang chạy.

![Cleanup ECS](/images/CleanUp/ECS.jpg)

---

2. Xóa **Amazon ECR Repository**.

+ Truy cập **Amazon ECR**.
+ Xóa Docker Images trong Repository.
+ Xóa Private Repository sau khi Repository không còn Image.

![Cleanup ECR](/images/CleanUp/ECR.jpg)

---

3. Xóa **Amazon EC2 Instance**.

+ Truy cập **Amazon EC2**.
+ Chọn EC2 Instance đã tạo.
+ Thực hiện **Terminate Instance**.

![Cleanup EC2](/images/CleanUp/EC2.jpg)

---

4. Xóa **Amazon RDS Database**.

+ Truy cập **Amazon RDS**.
+ Chọn Database Instance.
+ Tắt tùy chọn tạo Final Snapshot (nếu không cần lưu dữ liệu).
+ Xác nhận xóa Database.

![Cleanup RDS](/images/CleanUp/RDS.jpg)

---

5. Xóa **Amazon ElastiCache for Redis**.

+ Truy cập **Amazon ElastiCache**.
+ Chọn Redis Cluster.
+ Xóa Cache Cluster.

![Cleanup ElastiCache](/images/CleanUp/ElasticCache.jpg)

---

6. Xóa **IAM Role**.

+ Truy cập **AWS IAM**.
+ Chọn IAM Role đã sử dụng cho Amazon ECS.
+ Xóa Role sau khi các dịch vụ liên quan đã được gỡ bỏ.

![Cleanup IAM Role](/images/CleanUp/IAM_Role.jpg)

---

7. Xóa **Security Group**.

+ Truy cập **Amazon VPC**.
+ Chọn Security Group đã tạo cho hệ thống.
+ Xóa Security Group sau khi không còn tài nguyên sử dụng.

![Cleanup Security Group](/images/CleanUp/Security_Group.jpg)

---

8. Xóa **Subnets**.

+ Chọn các Public Subnets và Private Subnets đã tạo.
+ Thực hiện xóa toàn bộ Subnets.

![Cleanup Subnet](/images/CleanUp/Subnets.jpg)

---

9. Xóa **Route Table**.

+ Xóa các Route Tables đã tạo cho hệ thống.
+ Đảm bảo không còn liên kết với bất kỳ Subnet nào trước khi xóa.

![Cleanup Route Table](/images/CleanUp/Route_Table.jpg)

---

10. Xóa **Internet Gateway**.

+ Detach Internet Gateway khỏi Amazon VPC.
+ Xóa Internet Gateway.

![Cleanup Internet Gateway](/images/CleanUp/VPC_InternetGateway.jpg)

---

11. Xóa **Amazon VPC**.

+ Truy cập **Amazon VPC**.
+ Chọn VPC của hệ thống SportBooking.
+ Xóa VPC sau khi tất cả tài nguyên liên quan đã được gỡ bỏ.

![Cleanup VPC](/images/CleanUp/VPC.jpg)

---

#### Tóm tắt

Sau khi hoàn thành các bước trên, toàn bộ tài nguyên AWS của hệ thống **SportBooking** đã được dọn dẹp thành công. Việc xóa các tài nguyên sau khi hoàn tất quá trình triển khai và kiểm thử giúp tránh phát sinh chi phí không cần thiết, đồng thời đảm bảo môi trường AWS luôn sạch và sẵn sàng cho các lần triển khai tiếp theo.