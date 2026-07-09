---
title : "Tạo Amazon VPC"
date : 08-07-2026
weight : 1
chapter : false
pre : " <b> 5.3.1 </b> "
---

1. Đăng nhập vào **AWS Management Console** và mở dịch vụ **Amazon VPC**.

2. Trong thanh điều hướng bên trái, chọn **Your VPCs**, sau đó nhấn **Create VPC**.
![create VPC](/images/cloud/VPC/Yours_VPCs.jpg)
---

3. Trong cửa sổ **Create VPC**, tiến hành cấu hình các thông tin sau:

+ Chọn **VPC only** để tạo một VPC mới.
+ Nhập tên cho VPC.
+ Cấu hình **IPv4 CIDR Block** phù hợp với kiến trúc hệ thống.
+ Giữ nguyên các thiết lập còn lại theo mặc định.


---

4. Sau khi hoàn tất các thông tin cấu hình, nhấn **Create VPC** để tạo mạng riêng cho hệ thống.

AWS sẽ tự động khởi tạo VPC với các thông tin đã cấu hình.

![create VPC](/images/cloud/VPC/Create_VPC.jpg)

---

5. Sau khi tạo thành công, kiểm tra lại danh sách **Your VPCs** để xác nhận VPC đã được khởi tạo.

Đồng thời kiểm tra các thông tin như:

- VPC ID
- IPv4 CIDR Block
- State
- Default VPC
- Owner ID

Việc kiểm tra này giúp đảm bảo VPC đã được tạo thành công và sẵn sàng cho các bước cấu hình tiếp theo như tạo Subnet, Route Table, Internet Gateway và Security Group.

![create VPC](/images/cloud/VPC/Overview_Subnet.jpg)
![create VPC](/images/cloud/VPC/Internet_gateway.jpg)
![create VPC](/images/cloud/VPC/Route_Table.jpg)
![create VPC](/images/cloud/VPC/VPC_Subnet.jpg)
