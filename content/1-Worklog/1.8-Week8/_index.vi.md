---
title: "Worklog Tuần 8"
date: 05-06-2026
weight: 1
chapter: false
pre: " <b> 1.8. </b> "
---
{{% notice warning %}}
⚠️ **Lưu ý:** Các thông tin dưới đây chỉ nhằm mục đích tham khảo, vui lòng **không sao chép nguyên văn** cho bài báo cáo của bạn kể cả warning này.
{{% /notice %}}


### Mục tiêu tuần 8:

* Nghiên cứu IAM, Shared Responsibility Model và AWS Organizations.
* Tìm hiểu Amazon Cognito, AWS KMS và Security Hub.
* Thực hành IAM Role, CloudTrail, KMS và Security Hub.
* Tổng hợp toàn bộ kiến thức AWS Bootcamp.

### Các công việc cần triển khai trong tuần này:
| Thứ | Công việc                                                                                                                                                                                   | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu                            |
| --- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------ | --------------- | ----------------------------------------- |
| 2   | - Học Module 05 - 2.1:  Create Policy and Role <br>&emsp; + IAM Policies, Roles, Groups <br>&emsp; + Mô hình Shared Responsibility <br>&emsp; + AWS Organizations và chiến lược multi-account | 05/06/2026 | 05/06/2026 | <https://www.youtube.com/playlist?list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i> |
| 3   | - Học Module 05 - 2.2 :Create Group and User <br>&emsp; + Tạo IAM Group và gán Policy phù hợp với vai trò (ví dụ: AdministratorAccess hoặc ReadOnlyAccess).  <br>&emsp; + Tạo IAM User, thiết lập thông tin đăng nhập (Console hoặc Access Key nếu cần).<br>&emsp; | 06/06/2026 | 06/06/2026 | <https://www.youtube.com/playlist?list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i> |
| 4   | - Học Module 05 - 3.1: Create IAM Users <br>&emsp; + Nhập tên người dùng và cấu hình phương thức đăng nhập (AWS Management Console hoặc Programmatic Access nếu cần).<br>&emsp; + Gán người dùng vào IAM Group hoặc cấp quyền trực tiếp bằng IAM Policy. <br>&emsp; + Hoàn tất quá trình tạo và lưu thông tin đăng nhập để người dùng sử dụng.| 07/06/2026 | 07/06/2026 | <https://www.youtube.com/playlist?list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i> |
| 5   | - **Thực hành:** Lab - IAM Role cho EC2 <br>&emsp; + Tạo IAM Role và gắn cho EC2 <br>&emsp; + Cấu hình Policy theo nguyên tắc phân quyền tối thiểu <br>&emsp; + Kiểm tra EC2 truy cập dịch vụ AWS qua IAM Role | 08/06/2026 | 08/06/2026 | <https://000048.awsstudygroup.com/> |
| 6   | - **Thực hành:** Lab - CloudTrail,  Security Hub <br>&emsp; + Bật CloudTrail logging <br>&emsp;  + Bật Security Hub và xem xét security findings | 09/06/2026 | 09/06/2026 | <https://000033.awsstudygroup.com/> <br> <https://000018.awsstudygroup.com/> |
| 7   | - Tổng hợp kiến thức Module 05 (Security) <br>&emsp; + Ôn tập ghi chú và kiến thức trọng tâm <br> - Tổng hợp toàn bộ kiến thức AWS Bootcamp <br>&emsp; + Chuẩn bị áp dụng vào đề tài thực tập | 10/06/2026 | 11/06/2026 | <https://cloudjourney.awsstudygroup.com/> |


### Kết quả đạt được tuần 8:

* Hiểu chuyên sâu về các dịch vụ Security trên AWS:
  * IAM Policies, Roles, Groups và nguyên tắc least privilege
  * Shared Responsibility Model giữa AWS và khách hàng
  * AWS Organizations cho quản lý multi-account

* Nắm được các dịch vụ xác thực và mã hóa:
  * Amazon Cognito User Pools và Identity Pools
  * AWS KMS quản lý key và mã hóa dữ liệu
  * Security Hub quản lý tư thế bảo mật

* Hoàn thành các bài lab liên quan đến bảo mật:
  * Tạo IAM Role và gắn cho EC2 theo nguyên tắc least privilege
  * Bật CloudTrail ghi log hoạt động API
  * Tạo và quản lý KMS keys cho mã hóa
  * Bật Security Hub và xem xét security findings

* Tổng hợp toàn bộ kiến thức AWS Bootcamp:
  * Module 01: Cloud Fundamentals, IAM, Budgets
  * Module 02: Networking (VPC, Security Group, Route53)
  * Module 03: VPC Peering, Transit Gateway
  * Module 04: Compute (EC2, EBS, Auto Scaling)
  * Module 05: Storage (S3, CloudFront)
  * Module 06: Security (IAM, KMS, Security Hub)


