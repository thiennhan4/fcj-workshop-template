---
title: "Worklog Tuần 7"
date: 29-05-2026
weight: 1
chapter: false
pre: " <b> 1.7. </b> "
---
{{% notice warning %}}
⚠️ **Lưu ý:** Các thông tin dưới đây chỉ nhằm mục đích tham khảo, vui lòng **không sao chép nguyên văn** cho bài báo cáo của bạn kể cả warning này.
{{% /notice %}}


### Mục tiêu tuần 7:

* Nghiên cứu Amazon S3 và các Storage Class.
* Thực hành triển khai Static Website trên S3.
* Tìm hiểu CloudFront, Bucket Versioning và Cross Region Replication.

### Các công việc cần triển khai trong tuần này:
| Thứ | Công việc                                                                                                                                                                                   | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu                            |
| --- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------ | --------------- | ----------------------------------------- |
| 2   | - Học Module 05-01: Tổng quan Amazon S3 <br>&emsp; + Khái niệm S3: Buckets, Objects, Keys <br>&emsp; + Các Storage Class (Standard, IA, Glacier, Deep Archive) <br>&emsp; + Mô hình giá S3 | 29/05/2026 | 29/05/2026 | <https://www.youtube.com/playlist?list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i> |
| 3   | - **Thực hành:** Lab - Tạo S3 Bucket <br>&emsp; + Tạo S3 Bucket và cấu hình quyền truy cập cơ bản <br>&emsp; + Upload dữ liệu thử nghiệm <br>&emsp; + Cấu hình access control (ACL, Bucket Policy) | 30/05/2026 | 30/05/2026 | <https://000057.awsstudygroup.com/> |
| 4   | - **Thực hành:** Lab - Triển khai Static Website trên S3 <br>&emsp; + Bật Static Website Hosting trên S3 <br>&emsp; + Cấu hình index document và error document <br>&emsp; + Kiểm tra truy cập public | 31/05/2026 | 31/05/2026 | <https://000057.awsstudygroup.com/> |
| 5   | - **Thực hành:** Lab - Cấu hình Bucket Policy & CORS <br>&emsp; + Viết Bucket Policy để kiểm soát truy cập <br>&emsp; + Cấu hình CORS cho ứng dụng frontend <br>&emsp; + Kiểm tra cross-origin requests | 01/06/2026 | 01/06/2026 | <https://000057.awsstudygroup.com/> |
| 6   | - **Thực hành:** Lab - CloudFront phân phối nội dung <br>&emsp; + Tạo CloudFront Distribution <br>&emsp; + Cấu hình S3 làm Origin <br>&emsp; + Kiểm tra phân phối nội dung qua CloudFront | 02/06/2026 | 02/06/2026 | <https://000094.awsstudygroup.com/> |
| 7   | - **Thực hành:** Lab - Bucket Versioning & Cross Region Replication <br>&emsp; + Bật Bucket Versioning <br>&emsp; + Cấu hình Cross Region Replication (CRR) <br>&emsp; + Kiểm tra an toàn dữ liệu và hoàn thành Lab Storage | 03/06/2026 | 04/06/2026 | <https://000057.awsstudygroup.com/> |


### Kết quả đạt được tuần 7:

* Hiểu các kiến thức nền tảng về Amazon S3:
  * Khái niệm Bucket, Object, Key
  * Các Storage Class: Standard, Intelligent-Tiering, IA, Glacier, Deep Archive
  * Mô hình giá S3 và lifecycle policies

* Triển khai thành công Static Website trên S3:
  * Tạo và cấu hình S3 Bucket cho website hosting
  * Thiết lập Bucket Policy và CORS
  * Kiểm tra truy cập public từ ứng dụng frontend

* Hoàn thành bài lab CloudFront phân phối nội dung:
  * Tạo CloudFront Distribution với S3 làm Origin
  * Hiểu về CDN caching và edge locations

* Cấu hình bảo vệ dữ liệu:
  * Bật Bucket Versioning để khôi phục dữ liệu
  * Thiết lập Cross Region Replication cho disaster recovery
  * Tổng hợp toàn bộ kiến thức Storage trên AWS


