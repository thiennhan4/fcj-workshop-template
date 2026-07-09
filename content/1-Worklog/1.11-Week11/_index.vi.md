---
title: "Worklog Tuần 11"
date: 16-06-2026
weight: 2
chapter: false
pre: " <b> 1.11. </b> "
---
{{% notice warning %}}
⚠️ **Lưu ý:** Các thông tin dưới đây chỉ nhằm mục đích tham khảo, vui lòng **không sao chép nguyên văn** cho bài báo cáo của bạn kể cả warning này.
{{% /notice %}}


### Mục tiêu tuần 11:

* Khởi tạo dự án backend và thiết lập cấu trúc phân lớp.
* Triển khai kết nối cơ sở dữ liệu, xây dựng các entity và DTO.
* Xây dựng chức năng xác thực bằng JWT và hoàn thiện các API cốt lõi (User, Field, Booking, Payment).

### Các công việc cần triển khai trong tuần này:
| Thứ | Công việc                                                                                                                                                                                   | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu                            |
| --- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------ | --------------- | ----------------------------------------- |
| 2   | - Khởi tạo dự án Backend <br>&emsp; + Xây dựng cấu trúc thư mục dự án theo kiến trúc phân lớp (layered architecture) | 26/06/2026 | 26/06/2026 | |
| 3   | - Xây dựng các entity, DTO và cấu hình kết nối cơ sở dữ liệu <br>&emsp; + Thiết lập Connection Pool và cấu hình ORM | 27/06/2026 | 27/06/2026 | |
| 4   | - Xây dựng chức năng đăng ký, đăng nhập người dùng <br>&emsp; + Tích hợp JWT (JSON Web Tokens) cho bảo mật và xác thực | 28/06/2026 | 28/06/2026 | |
| 5   | - Xây dựng API quản lý người dùng và quản lý sân <br>&emsp; + Viết các endpoint CRUD cơ bản cho sân và tài khoản | 29/06/2026 | 29/06/2026 | |
| 6   | - Xây dựng API đặt sân (booking) và xử lý logic nghiệp vụ <br>&emsp; + Kiểm tra slots trống, tránh xung đột lịch đặt sân | 30/06/2026 | 30/06/2026 | |
| 7   | - Xây dựng service xử lý thanh toán <br>&emsp; + Cập nhật trạng thái đặt sân sau giao dịch thành công <br> - Rà soát, tối ưu code backend core và bổ sung validate dữ liệu đầu vào | 01/07/2026 | 02/07/2026 | |


### Kết quả đạt được tuần 11:

* Khởi tạo dự án backend cấu trúc phân lớp khoa học:
  * Phân tách rạch ròi các lớp: Controller, Service, Repository, Entity

* Cấu hình thành công tầng kết nối cơ sở dữ liệu:
  * Thiết lập các thực thể dữ liệu (entities) và DTOs tương ứng
  * Cấu hình connection pool giúp kết nối cơ sở dữ liệu ổn định

* Triển khai cơ chế xác thực và phân quyền:
  * Bảo mật hệ thống với cơ chế xác thực stateless bằng JWT
  * Phân quyền truy cập theo vai trò (Người dùng, Chủ sân, Quản trị viên)

* Phát triển hoàn thiện các API nghiệp vụ cốt lõi:
  * Các API CRUD quản lý người dùng và thông tin sân thể thao
  * API đặt sân với thuật toán kiểm tra xung đột slot và lịch đặt
  * Service xử lý thanh toán, cập nhật trạng thái đặt sân tự động khi nhận callback thanh toán

* Tối ưu hóa hiệu năng và bảo mật mã nguồn:
  * Bổ sung bộ lọc middleware để validate chặt chẽ dữ liệu đầu vào
  * Tối ưu hóa truy vấn SQL đảm bảo phản hồi API nhanh chóng
