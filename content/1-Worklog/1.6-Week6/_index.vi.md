---
title: "Worklog Tuần 6"
date: 22-05-2026
weight: 1
chapter: false
pre: " <b> 1.6. </b> "
---
{{% notice warning %}}
⚠️ **Lưu ý:** Các thông tin dưới đây chỉ nhằm mục đích tham khảo, vui lòng **không sao chép nguyên văn** cho bài báo cáo của bạn kể cả warning này.
{{% /notice %}}


### Mục tiêu tuần 6:

* Nghiên cứu chuyên sâu Amazon EC2: Instance Types, AMI, Key Pair.
* Tìm hiểu EBS, Instance Store, User Data, Auto Scaling, EFS.
* Thực hành AWS Backup để bảo vệ dữ liệu.

### Các công việc cần triển khai trong tuần này:
| Thứ | Công việc                                                                                                                                                                                   | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu                            |
| --- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------ | --------------- | ----------------------------------------- |
| 2   | - Học Module 04-01: Tổng quan Amazon EC2 <br>&emsp; + Các loại Instance Type và families <br>&emsp; + On-Demand, Reserved, Spot instances <br>&emsp; + Vòng đời instance | 22/05/2026 | 22/05/2026 | <https://www.youtube.com/playlist?list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i> |
| 3   | - Học Module 04-02: AMI & Key Pair <br>&emsp; + Tạo và quản lý AMI <br>&emsp; + Key Pair phục vụ xác thực SSH <br>&emsp; + AMI backup và khởi tạo instance | 23/05/2026 | 23/05/2026 | <https://www.youtube.com/playlist?list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i> |
| 4   | - Học Module 04-03: EBS & Instance Store <br>&emsp; + Các loại EBS volume (gp3, io2, st1, sc1) <br>&emsp; + EBS Snapshots <br>&emsp; + So sánh Instance Store và EBS | 24/05/2026 | 24/05/2026 | <https://www.youtube.com/playlist?list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i> |
| 5   | - Học Module 04-04: EC2 User Data <br>&emsp; + Tự động hóa cấu hình instance khi khởi động <br>&emsp; + Bootstrap scripts để cài đặt phần mềm | 25/05/2026 | 25/05/2026 | <https://www.youtube.com/playlist?list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i> |
| 6   | - Học Module 04-05: EC2 Auto Scaling, EFS & Amazon FSx <br>&emsp; + Auto Scaling Groups, launch templates <br>&emsp; + Amazon EFS cho lưu trữ file chia sẻ <br>&emsp; + Amazon FSx cho Windows và Lustre | 26/05/2026 | 26/05/2026 | <https://www.youtube.com/playlist?list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i> |
| 7   | - **Thực hành:** Lab - AWS Backup <br>&emsp; + Tạo Backup Plan với Snapshot tự động <br>&emsp; + Thực hiện Restore dữ liệu từ backup <br>&emsp; + Hoàn thành các Lab EC2 và AWS Backup | 27/05/2026 | 28/05/2026 | <https://000013.awsstudygroup.com/> <br> <https://000004.awsstudygroup.com/> |


### Kết quả đạt được tuần 6:

* Hiểu chuyên sâu về Amazon EC2:
  * Các loại Instance Type và families (General Purpose, Compute Optimized, Memory Optimized)
  * Mô hình giá: On-Demand, Reserved, Spot instances
  * Quản lý vòng đời instance

* Nắm được kiến thức AMI và storage:
  * Tạo, quản lý và chia sẻ AMI
  * Quản lý Key Pair cho xác thực SSH
  * Các loại EBS volume và trường hợp sử dụng
  * Khác biệt giữa Instance Store và EBS

* Hiểu tự động hóa và mở rộng EC2:
  * User Data scripts để cấu hình tự động khi khởi động
  * Auto Scaling Groups và launch templates
  * Amazon EFS cho lưu trữ file chia sẻ, tổng quan Amazon FSx

* Hoàn thành bài lab AWS Backup:
  * Tạo Backup Plan với lịch snapshot tự động
  * Thực hiện Restore dữ liệu từ snapshot
  * Hoàn thành tất cả các bài lab liên quan đến EC2


