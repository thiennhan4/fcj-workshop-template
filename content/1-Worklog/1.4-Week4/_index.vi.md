---
title: "Worklog Tuần 4"
date: 08-05-2026
weight: 1
chapter: false
pre: " <b> 1.4. </b> "
---
{{% notice warning %}}
⚠️ **Lưu ý:** Các thông tin dưới đây chỉ nhằm mục đích tham khảo, vui lòng **không sao chép nguyên văn** cho bài báo cáo của bạn kể cả warning này.
{{% /notice %}}


### Mục tiêu tuần 4:

* Thực hành triển khai EC2 instance và kết nối SSH.
* Nghiên cứu kiến trúc Hybrid DNS với Route 53 Resolver.
* Tìm hiểu Infrastructure as Code với AWS CloudFormation.

### Các công việc cần triển khai trong tuần này:
| Thứ | Công việc                                                                                                                                                                                   | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu                            |
| --- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------ | --------------- | ----------------------------------------- |
| 2   | - **Thực hành:** Lab - Triển khai EC2 trong Public Subnet <br>&emsp; + Khởi tạo EC2 instance trong Public Subnet <br>&emsp; + Gán Elastic IP và kiểm tra kết nối Internet | 08/05/2026 | 08/05/2026 | <https://000004.awsstudygroup.com/> |
| 3   | - **Thực hành:** Lab - Kết nối SSH & EC2 Instance Connect <br>&emsp; + Kết nối EC2 qua SSH Key Pair <br>&emsp; + Kiểm tra EC2 Instance Connect Endpoint | 09/05/2026 | 09/05/2026 | <https://000004.awsstudygroup.com/> |
| 4   | - Học Module 02: Kiến trúc Hybrid DNS <br>&emsp; + Cơ chế phân giải DNS giữa on-premise và AWS Cloud <br>&emsp; + Route 53 Resolver Inbound/Outbound Endpoints | 10/05/2026 | 10/05/2026 | <https://www.youtube.com/playlist?list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i> |
| 5   | - Học Module: Infrastructure as Code với CloudFormation <br>&emsp; + Cấu trúc template CloudFormation (YAML/JSON) <br>&emsp; + Tạo và quản lý Stack | 11/05/2026 | 11/05/2026 | <https://www.youtube.com/playlist?list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i> |
| 6   | - **Thực hành:** Lab - Cấu hình Route53 Resolver & DNS Rules <br>&emsp; + Tạo Route53 Resolver Inbound/Outbound Endpoints <br>&emsp; + Cấu hình DNS forwarding rules <br>&emsp; + Kiểm tra và xử lý lỗi phân giải DNS | 12/05/2026 | 13/05/2026 | <https://000010.awsstudygroup.com/> |
| 7   | - Tổng hợp kiến thức Networking <br>&emsp; + Hoàn thành các bài Lab Module 01 và Module 02 <br>&emsp; + Tóm tắt kiến thức trọng tâm và best practices | 14/05/2026 | 14/05/2026 | <https://000003.awsstudygroup.com/> <br> <https://000010.awsstudygroup.com/> |


### Kết quả đạt được tuần 4:

* Triển khai thành công EC2 instance trong Public Subnet:
  * Khởi tạo EC2 instance và gán Elastic IP
  * Kiểm tra kết nối Internet từ instance
  * Kết nối qua SSH và EC2 Instance Connect Endpoint

* Hiểu kiến trúc Hybrid DNS trên AWS:
  * Cơ chế phân giải DNS giữa on-premise và AWS Cloud
  * Route 53 Resolver Inbound và Outbound Endpoints
  * Cấu hình DNS forwarding rules

* Tìm hiểu Infrastructure as Code với CloudFormation:
  * Cấu trúc template (định dạng YAML/JSON)
  * Tạo, cập nhật và xóa Stack

* Hoàn thành bài lab Route53 Resolver:
  * Cấu hình Resolver Endpoints và DNS Rules
  * Kiểm tra và xử lý các lỗi phân giải DNS

* Tổng hợp toàn bộ kiến thức Networking từ Module 01 và Module 02.


