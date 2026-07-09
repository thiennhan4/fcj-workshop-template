---
title : "Tạo Public Subnet và Private Subnet"
date : 08-07-2026
weight : 2
chapter : false
pre : " <b> 5.3.2 </b> "
---

#### Tạo Public Subnet

1. Mở **Amazon VPC Console**.

2. Trong thanh điều hướng bên trái, chọn **Subnets**, sau đó nhấn **Create subnet**.

*Chèn hình ảnh giao diện Subnets tại đây.*

3. Trong cửa sổ **Create subnet**, thực hiện các cấu hình sau:

+ Chọn **VPC** đã tạo ở bước trước.
+ Nhập tên cho Public Subnet.
+ Chọn **Availability Zone (AZ)** phù hợp.
+ Cấu hình **IPv4 CIDR Block**.

Sau khi hoàn tất, nhấn **Create subnet** để tạo Public Subnet.

![create VPC](/images/cloud/VPC/VPC_Subnet.jpg)

---

#### Tạo Private Subnet

1. Tiếp tục chọn **Create subnet** để tạo Private Subnet.

2. Trong cửa sổ **Create subnet**, thực hiện các cấu hình sau:

+ Chọn cùng **VPC** đã tạo.
+ Nhập tên cho Private Subnet.
+ Chọn Availability Zone tương ứng.
+ Cấu hình IPv4 CIDR Block khác với Public Subnet để tránh trùng lặp địa chỉ IP.

Sau khi hoàn tất, nhấn **Create subnet**.

![create VPC](/images/cloud/VPC/Yours_VPCs.jpg)

---

#### Kiểm tra các Subnet

Sau khi tạo thành công, quay lại danh sách **Subnets** để kiểm tra các tài nguyên vừa tạo.

Đảm bảo hệ thống đã có đầy đủ:

- Public Subnet 1
- Public Subnet 2
- Private Subnet 1
- Private Subnet 2

Đồng thời kiểm tra các thông tin:

- Subnet ID
- Availability Zone
- IPv4 CIDR Block
- VPC
- State

![create VPC](/images/cloud/VPC/Overview_Subnet.jpg)
![create VPC](/images/cloud/VPC/Overview_YoursVPC.jpg)
---

#### Tóm tắt

Sau khi hoàn thành bước này, hệ thống đã được cấu hình đầy đủ các Public Subnet và Private Subnet trong Amazon VPC.

Các Public Subnet sẽ được sử dụng để triển khai các tài nguyên cần kết nối Internet như Application Load Balancer và NAT Gateway. Trong khi đó, các Private Subnet sẽ được sử dụng để triển khai Amazon ECS, Amazon RDS PostgreSQL và Amazon ElastiCache Redis nhằm tăng cường tính bảo mật cho hệ thống.

Việc phân tách Public Subnet và Private Subnet giúp kiến trúc hạ tầng của hệ thống SportBooking tuân theo các khuyến nghị của AWS về tính bảo mật, khả năng mở rộng và tính sẵn sàng cao.