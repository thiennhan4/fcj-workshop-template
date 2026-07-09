---
title : "Triển khai hạ tầng mạng AWS"
date : 08-07-2026
weight : 3
chapter : false
pre : " <b> 5.3. </b> "
---

#### Tổng quan

Trong phần này, thành viên trong nhóm  tiến hành triển khai hạ tầng mạng cho hệ thống **SportBooking** trên nền tảng AWS. Mục tiêu là xây dựng một môi trường mạng riêng (Amazon VPC) nhằm đảm bảo tính bảo mật, khả năng mở rộng và đáp ứng yêu cầu triển khai các dịch vụ của hệ thống.

Hạ tầng mạng được xây dựng bao gồm Amazon VPC, Public Subnet, Private Subnet, Internet Gateway, Security Group , NAT Gateway và Route Table. Các thành phần này phối hợp với nhau để tạo nên một kiến trúc mạng an toàn, trong đó các tài nguyên cần truy cập Internet được đặt trong Public Subnet, còn các dịch vụ backend và cơ sở dữ liệu được triển khai trong Private Subnet.

![Cấu trúc sơ đồ VPC](/images/diagram_vpc.jpg)

#### Nội dung

- [Tạo Amazon VPC](3.1-create-vpc/)
![VPC](/images/cloud/VPC/Create_VPC.jpg)
- [Tạo Public Subnet và Private Subnet](3.2-create-subnets/)
![VPC](/images/cloud/VPC/Yours_VPCs.jpg)
![VPC](/images/cloud/VPC/VPC_Subnet.jpg)
- [Cấu hình Internet Gateway, Security Group và Route Table](3.3-network-configuration/)
![VPC Interner Gateway](/images/cloud/VPC/Internet_gateway.jpg)
![ VPC - Route Table](/images/cloud/VPC/Route_Table.jpg)
![ VPC - Security Group](/images/cloud/VPC/security_group.jpg)
