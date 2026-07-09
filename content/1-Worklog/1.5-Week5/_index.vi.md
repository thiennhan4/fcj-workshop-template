---
title: "Worklog Tuần 5"
date: 15-05-2026
weight: 1
chapter: false
pre: " <b> 1.5. </b> "
---
{{% notice warning %}}
⚠️ **Lưu ý:** Các thông tin dưới đây chỉ nhằm mục đích tham khảo, vui lòng **không sao chép nguyên văn** cho bài báo cáo của bạn kể cả warning này.
{{% /notice %}}


### Mục tiêu tuần 5:

* Nghiên cứu VPC Peering và các trường hợp sử dụng.
* Nghiên cứu AWS Transit Gateway và so sánh với VPC Peering.
* Thực hành cấu hình VPC Peering và Transit Gateway.

### Các công việc cần triển khai trong tuần này:
| Thứ | Công việc                                                                                                                                                                                   | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu                            |
| --- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------ | --------------- | ----------------------------------------- |
| 2   | - Học Module 03: VPC Peering <br>&emsp; + Khái niệm và các trường hợp sử dụng VPC Peering <br>&emsp; + Cross-Region và Cross-Account peering <br>&emsp; + Giới hạn và lưu ý về định tuyến | 15/05/2026 | 15/05/2026 | <https://www.youtube.com/playlist?list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i> |
| 3   | - **Thực hành:** Lab - Tạo VPC Peering Connection <br>&emsp; + Tạo VPC Peering giữa hai VPC khác Region <br>&emsp; + Chấp nhận peering request và kiểm tra kết nối | 16/05/2026 | 16/05/2026 | <https://000019.awsstudygroup.com/> |
| 4   | - **Thực hành:** Lab - Cấu hình Route Table cho VPC Peering <br>&emsp; + Cập nhật Route Table ở cả hai VPC <br>&emsp; + Kiểm tra giao tiếp cross-VPC giữa các EC2 | 17/05/2026 | 17/05/2026 | <https://000019.awsstudygroup.com/> |
| 5   | - Học Module 03: AWS Transit Gateway <br>&emsp; + Kiến trúc và khái niệm Transit Gateway <br>&emsp; + So sánh với mô hình VPC Peering truyền thống <br>&emsp; + Mô hình mạng hub-and-spoke | 18/05/2026 | 18/05/2026 | <https://www.youtube.com/playlist?list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i> |
| 6   | - **Thực hành:** Lab - Tạo Transit Gateway & Attachments <br>&emsp; + Tạo Transit Gateway <br>&emsp; + Tạo Transit Gateway Attachment cho nhiều VPC <br>&emsp; + Cấu hình Transit Gateway Route Table | 19/05/2026 | 20/05/2026 | <https://000020.awsstudygroup.com/> |
| 7   | - **Thực hành:** Hoàn thành Lab Transit Gateway <br>&emsp; + Kiểm tra định tuyến giữa các VPC đính kèm <br>&emsp; + Test kết nối cross-VPC <br>&emsp; + Dọn dẹp tài nguyên | 21/05/2026 | 21/05/2026 | <https://000020.awsstudygroup.com/> |


### Kết quả đạt được tuần 5:

* Hiểu khái niệm VPC Peering:
  * Các loại VPC Peering (cùng Region, khác Region, khác Account)
  * Cấu hình định tuyến cho các VPC đã peering
  * Giới hạn: không hỗ trợ transitive peering

* Hoàn thành thành công bài lab VPC Peering:
  * Tạo VPC Peering Connection giữa hai VPC khác Region
  * Cấu hình Route Table và kiểm tra giao tiếp cross-VPC

* Hiểu kiến trúc AWS Transit Gateway:
  * Mô hình hub-and-spoke để quản lý mạng tập trung
  * Ưu điểm so với mô hình VPC Peering truyền thống
  * Khái niệm Transit Gateway Route Table

* Hoàn thành thành công bài lab Transit Gateway:
  * Tạo Transit Gateway và đính kèm nhiều VPC
  * Cấu hình Transit Gateway Route Table
  * Kiểm tra định tuyến giữa tất cả VPC đính kèm
  * Dọn dẹp tài nguyên sau khi hoàn thành lab


