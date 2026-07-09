---
title: "Worklog Tuần 3"
date: 01-05-2026
weight: 1
chapter: false
pre: " <b> 1.3. </b> "
---
{{% notice warning %}}
⚠️ **Lưu ý:** Các thông tin dưới đây chỉ nhằm mục đích tham khảo, vui lòng **không sao chép nguyên văn** cho bài báo cáo của bạn kể cả warning này.
{{% /notice %}}


### Mục tiêu tuần 3:

* Nghiên cứu Amazon VPC và kiến trúc mạng trên AWS.
* Hiểu Security Group, Network ACL và các thành phần mạng.
* Thực hành tạo và cấu hình VPC, Subnet, Route Table, Gateway.

### Các công việc cần triển khai trong tuần này:
| Thứ | Công việc                                                                                                                                                                                   | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu                            |
| --- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------ | --------------- | ----------------------------------------- |
| 2   | - Học Module 02-01: Tổng quan Amazon VPC <br>&emsp; + Khái niệm VPC, CIDR block <br>&emsp; + Public Subnet vs Private Subnet <br>&emsp; + Internet Gateway và NAT Gateway | 01/05/2026 | 01/05/2026 | <https://www.youtube.com/playlist?list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i> |
| 3   | - Học Module 02-02: Security Group & Network ACL <br>&emsp; + Firewall Stateful vs Stateless <br>&emsp; + Inbound/Outbound rules <br>&emsp; + So sánh SG và NACL | 02/05/2026 | 02/05/2026 | <https://www.youtube.com/playlist?list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i> |
| 4   | - Học Module 02-03: VPN, Direct Connect, Load Balancer <br>&emsp; + Site-to-Site VPN <br>&emsp; + AWS Direct Connect <br>&emsp; + Các loại Elastic Load Balancing | 03/05/2026 | 03/05/2026 | <https://www.youtube.com/playlist?list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i> |
| 5   | - **Thực hành:** Lab - Tạo VPC tùy chỉnh <br>&emsp; + Tạo VPC với CIDR block tùy chỉnh <br>&emsp; + Tạo Subnet theo từng Availability Zone <br>&emsp; + Cấu hình Route Table và Internet Gateway | 04/05/2026 | 05/05/2026 | <https://000003.awsstudygroup.com/> |
| 6   | - **Thực hành:** Lab - Triển khai NAT Gateway <br>&emsp; + Triển khai NAT Gateway trong Public Subnet  | 06/05/2026 | 06/05/2026 | <https://000003.awsstudygroup.com/> |
| 7   | - **Thực hành:** Lab - Kiểm tra khả năng truy cập Internet từ Private Subnet <br>&emsp; + Cấu hình Security Group và Network ACL | 07/05/2026 | 07/05/2026 | <https://000003.awsstudygroup.com/> |



### Kết quả đạt được tuần 3:

* Hiểu các kiến thức nền tảng về Amazon VPC:
  * Khái niệm VPC, Subnet, CIDR block
  * Kiến trúc Public Subnet vs Private Subnet
  * Vai trò của Internet Gateway và NAT Gateway

* Nắm được cơ chế bảo mật trong VPC:
  * Security Group (stateful) vs Network ACL (stateless)
  * Cấu hình Inbound/Outbound rules
  * Khái niệm VPN, Direct Connect và Load Balancer

* Thực hành thành công bài lab VPC:
  * Tạo VPC tùy chỉnh với chia CIDR block
  * Tạo Subnet trên nhiều Availability Zone
  * Cấu hình Route Table và Internet Gateway
  * Triển khai NAT Gateway và kiểm tra truy cập Internet từ Private Subnet
  * Cấu hình Security Group, Network ACL và kiểm tra kết nối giữa các EC2


