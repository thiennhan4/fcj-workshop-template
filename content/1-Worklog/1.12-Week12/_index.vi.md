---
title: "Worklog Tuần 12"
date: 03-07-2026
weight: 2
chapter: false
pre: " <b> 1.12. </b> "
---
{{% notice warning %}}
⚠️ **Lưu ý:** Các thông tin dưới đây chỉ nhằm mục đích tham khảo, vui lòng **không sao chép nguyên văn** cho bài báo cáo của bạn kể cả warning này.
{{% /notice %}}


### Mục tiêu tuần 12:

* Triển khai ứng dụng backend và cơ sở dữ liệu lên dịch vụ AWS (EC2 và RDS).
* Cấu hình S3 và CloudFront để lưu trữ/phân phối hình ảnh sân.
* Kiểm thử toàn bộ hệ thống (xác thực, đặt sân, thanh toán, triển khai).
* Hoàn thiện báo cáo cuối khóa và bàn giao dự án.

### Các công việc cần triển khai trong tuần này:
| Thứ | Công việc                                                                                                                                                                                   | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu                            |
| --- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------ | --------------- | ----------------------------------------- |
| 2   | - Nghiên cứu cách triển khai backend lên Amazon EC2 <br>&emsp; + Cấu hình security group cho EC2 và khởi chạy instance <br>&emsp; + Kéo code và chạy thử backend trên server | 03/07/2026 | 03/07/2026 | <https://000004.awsstudygroup.com/> |
| 3   | - Thực hành chạy thử dịch vụ Amazon RDS <br>&emsp; + Tạo cơ sở dữ liệu SQL Server trên RDS <br>&emsp; + Bảo mật kết nối từ backend (EC2) đến database trên RDS | 04/07/2026 | 04/07/2026 | <https://000005.awsstudygroup.com/> |
| 4   | - Nghiên cứu và cấu hình Amazon S3, CloudFront để lưu trữ/phân phối hình ảnh sân <br>&emsp; + Tạo S3 bucket lưu trữ ảnh sân <br>&emsp; + Cấu hình CloudFront distribution để phân phối ảnh hiệu năng cao | 05/07/2026 | 05/07/2026 | <https://000057.awsstudygroup.com/> <br> <https://000094.awsstudygroup.com/> |
| 5   | - Kiểm thử chức năng đăng ký, đăng nhập và phân quyền của hệ thống <br>&emsp; + Kiểm thử quy trình đặt sân, thanh toán và quản lý lịch đặt | 06/07/2026 | 07/07/2026 | |
| 6   | - Kiểm thử khả năng triển khai hệ thống trên AWS <br>&emsp; + Ghi nhận và xử lý lỗi phát sinh khi chạy thực tế | 08/07/2026 | 08/07/2026 | |
| 7   | - Tổng hợp kết quả nghiên cứu, hoàn thiện tài liệu kỹ thuật và mã nguồn <br> - Nộp báo cáo thực tập, bàn giao mã nguồn và tổng kết quá trình thực tập | 09/07/2026 | 10/07/2026 | |


### Kết quả đạt được tuần 12:

* Triển khai thành công ứng dụng và cơ sở dữ liệu lên AWS:
  * Chạy thử và kết nối backend thành công với dịch vụ Amazon RDS
  * Deploy ứng dụng backend chạy ổn định trên Amazon EC2 nằm trong VPC bảo mật

* Cấu hình lưu trữ đám mây và phân phối nội dung:
  * Tích hợp thành công Amazon S3 để lưu trữ dữ liệu ảnh sân thể thao
  * Sử dụng CloudFront để cache và phân phối hình ảnh với độ trễ tối thiểu

* Kiểm thử toàn diện hệ thống:
  * Xác thực thành công luồng đăng ký, đăng nhập và phân quyền bảo mật người dùng
  * Kiểm thử thành công tính năng đặt sân, thanh toán và xử lý callback trạng thái booking
  * Phát hiện và khắc phục các cấu hình định tuyến trên AWS

* Hoàn thành sản phẩm bàn giao thực tập:
  * Hoàn thành tài liệu kỹ thuật chi tiết và báo cáo thực tập tổng kết kiến thức AWS
  * Bàn giao mã nguồn hoàn chỉnh, cấu hình hạ tầng và kết thúc kỳ thực tập tốt đẹp
