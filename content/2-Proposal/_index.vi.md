---
title: "Bản đề xuất"
date : 08-07-2026
weight: 2
chapter: false
pre: " <b> 2. </b> "
---

# Hệ thống đặt sân thể thao

## Giải pháp triển khai ứng dụng Web trên AWS

### 1. Tóm tắt điều hành

Hệ thống đặt sân thể thao được xây dựng nhằm hỗ trợ người dùng tìm kiếm, đặt sân và quản lý lịch sử đặt sân trực tuyến thông qua nền tảng web. Hệ thống được triển khai trên hạ tầng AWS theo kiến trúc nhiều lớp (Multi-tier Architecture), đảm bảo tính sẵn sàng cao, bảo mật và khả năng mở rộng.

Kiến trúc sử dụng Amazon ECS để triển khai ứng dụng dưới dạng container, Amazon RDS làm cơ sở dữ liệu, Redis để lưu cache, Amazon S3 lưu trữ tệp tĩnh và hình ảnh, CloudFront giúp phân phối nội dung nhanh hơn và Route 53 quản lý tên miền. Hệ thống được bảo vệ bởi AWS WAF và AWS Certificate Manager cung cấp chứng chỉ SSL.

---

## 2. Tuyên bố vấn đề

### Vấn đề hiện tại

Nhiều sân thể thao vẫn quản lý lịch đặt sân bằng điện thoại hoặc sổ sách dẫn đến:

- Khó quản lý lịch đặt.
- Dễ xảy ra trùng lịch.
- Không có hệ thống thanh toán và quản lý tập trung.
- Khó mở rộng khi số lượng sân tăng.
- Không đảm bảo tính sẵn sàng khi lượng người truy cập lớn.

### Giải pháp

Giải pháp triển khai hệ thống trên AWS với kiến trúc Cloud Native.

Người dùng truy cập website thông qua Route 53 và CloudFront.

CloudFront kết hợp AWS WAF để tăng tốc độ truy cập và chống các cuộc tấn công Web.

Application Load Balancer phân phối yêu cầu đến các container chạy trên Amazon ECS.

Ứng dụng truy cập cơ sở dữ liệu Amazon RDS đặt trong Private Subnet.

Redis được sử dụng để cache dữ liệu nhằm giảm tải Database.

Hình ảnh và tài nguyên tĩnh được lưu trữ trên Amazon S3.

Amazon ECR lưu Docker Image của ứng dụng.

AWS Secrets Manager lưu thông tin Database và các khóa bí mật.

Amazon CloudWatch theo dõi toàn bộ hệ thống và gửi cảnh báo qua Amazon SNS.

### Lợi ích

- Tự động mở rộng hệ thống.
- Bảo mật cao.
- Đảm bảo tính sẵn sàng.
- Dễ triển khai phiên bản mới.
- Giảm thời gian quản trị hệ thống.
- Tăng hiệu suất truy cập nhờ CloudFront và Redis.

---

## 3. Kiến trúc giải pháp

Hệ thống được triển khai trong một Amazon VPC bao gồm Public Subnet và Private Subnet trên hai Availability Zone nhằm đảm bảo tính sẵn sàng cao.

Luồng hoạt động của hệ thống như sau:

1. Người dùng truy cập website thông qua Route 53.

2. CloudFront phân phối nội dung và giảm độ trễ.

3. AWS WAF kiểm tra và lọc các yêu cầu độc hại.

4. Các yêu cầu hợp lệ được chuyển đến Application Load Balancer.

5. ALB phân phối lưu lượng đến các container chạy trên Amazon ECS.

6. ECS xử lý nghiệp vụ của hệ thống.

7. Dữ liệu được lưu trong Amazon RDS (Primary DB).

8. Redis cache dữ liệu thường xuyên truy cập.

9. Amazon RDS Standby tại Availability Zone thứ hai đảm bảo khả năng khôi phục khi xảy ra sự cố.

10. Amazon S3 lưu trữ giao diện frontend và các tệp người dùng tải lên.

11. Docker Image của ứng dụng được lưu trên Amazon ECR.

12. AWS Secrets Manager quản lý thông tin đăng nhập Database.

13. Amazon CloudWatch giám sát toàn bộ tài nguyên.

14. Amazon SNS gửi email cảnh báo cho quản trị viên khi hệ thống phát sinh lỗi.

![Kiến trúc hệ thống](/images/diagram_aws.jpg)

### Dịch vụ AWS sử dụng

- Amazon Route 53
- Amazon CloudFront
- AWS WAF
- AWS Certificate Manager
- Amazon S3
- Amazon VPC
- Public Subnet
- Private Subnet
- NAT Gateway
- Application Load Balancer
- Amazon ECS
- Amazon RDS
- Amazon ElastiCache for Redis
- Amazon ECR
- AWS Secrets Manager
- Amazon CloudWatch
- Amazon SNS

### Thiết kế thành phần

**Edge Layer**

- Route 53 quản lý tên miền.
- CloudFront phân phối nội dung.
- AWS WAF bảo vệ ứng dụng.
- ACM cung cấp SSL.
- Amazon S3 lưu trữ Frontend và Uploads.

**Application Layer**

- ALB cân bằng tải.
- Amazon ECS chạy Backend.
- Amazon ECR lưu Docker Image.

**Database Layer**

- Amazon RDS Primary.
- Amazon RDS Standby.
- Redis Cache.

**Monitoring Layer**

- CloudWatch giám sát.
- SNS gửi Email cảnh báo.

---

## 4. Triển khai kỹ thuật

### Giai đoạn 1

- Phân tích yêu cầu.
- Thiết kế cơ sở dữ liệu.
- Thiết kế kiến trúc AWS.

### Giai đoạn 2

- Tạo VPC.
- Cấu hình Subnet.
- NAT Gateway.
- Security Group.

### Giai đoạn 3

- Triển khai Amazon ECS.
- Đưa Docker Image lên Amazon ECR.
- Cấu hình Application Load Balancer.

### Giai đoạn 4

- Triển khai Amazon RDS.
- Redis.
- Secrets Manager.

### Giai đoạn 5

- Cấu hình CloudFront.
- Route53.
- AWS WAF.
- ACM.

### Giai đoạn 6

- Thiết lập CloudWatch.
- SNS.
- Kiểm thử.
- Đưa hệ thống vào vận hành.

---

## 5. Lộ trình triển khai

| Giai đoạn | Nội dung |
|-----------|----------|
| Tháng 1 | Thiết kế hệ thống |
| Tháng 2 | Xây dựng Backend và Database |
| Tháng 3 | Triển khai ECS và RDS |
| Tháng 4 | Kiểm thử và triển khai thực tế |

---

## 6. Ước tính ngân sách

Chi phí bao gồm:

- Amazon ECS
- Amazon RDS
- Amazon ElastiCache
- Amazon CloudFront
- Route53
- S3
- NAT Gateway
- Application Load Balancer
- CloudWatch
- SNS

Tổng chi phí phụ thuộc vào cấu hình EC2/ECS, dung lượng cơ sở dữ liệu và lưu lượng truy cập thực tế.

---

## 7. Đánh giá rủi ro

### Rủi ro

- ECS gặp sự cố.
- Database quá tải.
- Redis lỗi.
- Tấn công DDoS.
- Hết dung lượng Database.

### Giải pháp

- ECS chạy trên nhiều Availability Zone.
- RDS Multi-AZ.
- CloudFront giảm tải.
- AWS WAF chống tấn công.
- CloudWatch giám sát và SNS gửi cảnh báo.

---

## 8. Kết quả kỳ vọng

- Hệ thống hoạt động ổn định 24/7.
- Có khả năng mở rộng khi lượng người dùng tăng.
- Đảm bảo tính bảo mật.
- Giảm thời gian triển khai nhờ Docker và ECS.
- Đảm bảo dữ liệu luôn sẵn sàng với RDS Multi-AZ.
- Dễ dàng bảo trì và nâng cấp trong tương lai.