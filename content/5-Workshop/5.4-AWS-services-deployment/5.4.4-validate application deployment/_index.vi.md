---
title : "Kiểm tra triển khai ứng dụng"
date : 08-07-2026
weight : 4
chapter : false
pre : " <b> 5.4.4 </b> "
---

Trong phần này, tôi tiến hành kiểm tra ứng dụng SportBooking sau khi hoàn tất quá trình triển khai nhằm xác nhận hệ thống hoạt động ổn định trên nền tảng AWS.

#### Kiểm tra API

+ Truy cập API thông qua Application Load Balancer.
+ Gửi yêu cầu đến các API của hệ thống.
+ Kiểm tra kết quả phản hồi từ ứng dụng.

![API - ALB](/images/cloud/ALB/alb.jpg)
![API](/images/Api/test_api.jpg)
![API](/images/Api/test_api1.jpg)
![API](/images/Api/test_api2.jpg)
![API](/images/Api/test_api3.jpg)
![API](/images/Api/test_api4.jpg)
![API](/images/Api/test_api5.jpg)
![Swagger](/images/Api/swagger.jpg)
---

#### Kiểm tra kết nối cơ sở dữ liệu

+ Kiểm tra ứng dụng có thể kết nối đến Amazon Aurora SQL Server/ Amazon RDS.
+ Xác nhận dữ liệu được truy xuất và lưu trữ thành công.
![RDS](/images/cloud/RDS/RDS.jpg)

---

#### Kiểm tra Redis

+ Kiểm tra ứng dụng có thể kết nối đến Amazon ElastiCache for Redis.
+ Xác nhận Redis hoạt động ổn định trong quá trình vận hành.
![Redis](/images/cloud/Redis/Redis.jpg)
![ElastiCache](/images/cloud/ElastiCache/ElastiCache.jpg)

---
#### Kiểm tra AWS CLI

Sau khi hoàn tất cấu hình AWS CLI, tôi tiến hành kiểm tra thông tin cấu hình và xác thực tài khoản AWS nhằm đảm bảo môi trường triển khai đã sẵn sàng.

Các nội dung kiểm tra bao gồm:

- Phiên bản AWS CLI.
- Thông tin cấu hình (Access Key, Region).
- Xác thực tài khoản AWS.
- Quyền truy cập vào các dịch vụ AWS.

![AWS CLI](/images/aws_cli.jpg)
![AWS CLI](/images/aws_cli_sts_get_caller_identity.jpg)
---

#### Kết quả triển khai

Sau khi hoàn thành các bước kiểm tra, hệ thống SportBooking đã được triển khai thành công trên nền tảng AWS. Các dịch vụ hoạt động ổn định, ứng dụng có thể truy cập, kết nối cơ sở dữ liệu và thực hiện các chức năng theo thiết kế .
