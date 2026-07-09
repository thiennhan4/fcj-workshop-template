---
title: "Blog 3"
date: 08-07-2026
weight: 3
chapter: false
pre: " <b> 3.3. </b> "
---


# CẢI THIỆN HIỆU SUẤT ỨNG DỤNG VỚI CDN CACHING TRONG AWS AMPLIFY HOSTING

Trong quá trình tìm hiểu về **AWS Amplify Hosting**, mình đọc được bài viết **"CDN Caching Improvements for Better App Performance with AWS Amplify Hosting"** trên AWS Front-End Web & Mobile Blog. Điều mình thấy ấn tượng nhất là AWS đã tối ưu cơ chế CDN Caching trên Amplify Hosting nhằm tăng tốc độ tải website mà không yêu cầu lập trình viên phải thay đổi nhiều trong mã nguồn ứng dụng.

Các cải tiến này tập trung vào việc nâng cao **Cache Hit Ratio**, giảm số lượng request phải chuyển về Origin Server và tận dụng tối đa mạng phân phối nội dung **Amazon CloudFront**. Điều này giúp người dùng truy cập website nhanh hơn, đồng thời giảm tải cho máy chủ phía sau.

---

## 1. Bài toán

Đối với các website hiện đại, đặc biệt là các ứng dụng React, Next.js hoặc Static Site, CDN đóng vai trò rất quan trọng trong việc phân phối nội dung.

Thông thường, khi người dùng truy cập website, CloudFront sẽ kiểm tra xem nội dung đã được lưu trong bộ nhớ đệm (Cache) hay chưa.

- Nếu dữ liệu đã có trong Cache (Cache Hit), CloudFront sẽ trả về ngay từ Edge Location gần người dùng nhất.
- Nếu chưa có (Cache Miss), CloudFront sẽ gửi request về Origin Server để lấy dữ liệu rồi lưu lại cho những lần truy cập tiếp theo.

Tuy nhiên, nhiều ứng dụng lại có **Cache Hit Ratio thấp** do Cache Key chứa quá nhiều thông tin không cần thiết, đặc biệt là **Cookies**.

Ví dụ:

- Google Analytics
- Session Cookies
- Tracking Cookies

Mỗi người dùng sẽ có giá trị Cookie khác nhau. Nếu Cookie được đưa vào Cache Key thì cùng một trang web sẽ được xem là nhiều request khác nhau, khiến CloudFront không thể tái sử dụng dữ liệu đã cache.

Điều này làm:

- Tăng số lượng Cache Miss.
- Origin Server phải xử lý nhiều request hơn.
- Tăng độ trễ.
- Làm giảm hiệu năng của ứng dụng.

---

## 2. Giải pháp của AWS

Để giải quyết vấn đề trên, AWS đã cải tiến cơ chế Cache của Amplify Hosting thông qua nhiều tính năng mới.

### Tối ưu Cache Policies

Amplify Hosting sử dụng các Cache Policy khác nhau cho từng loại nội dung như:

- Static Content
- Server-Side Rendering (SSR)
- Image Optimization

Mỗi loại nội dung đều có thời gian lưu cache (TTL) và Cache Key riêng, giúp tối ưu hiệu quả lưu trữ và phân phối dữ liệu.

---

### Loại bỏ Cookies khỏi Cache Key

Đây là cải tiến quan trọng nhất trong bản cập nhật.

Thay vì đưa toàn bộ Cookies vào Cache Key như trước, Amplify Hosting cho phép loại bỏ Cookies không cần thiết.

Ví dụ:

```
https://example.com

Cookie:
ga-session-id=123456
```

Trước đây mỗi Cookie sẽ tạo ra một Cache Key khác nhau.

Sau khi loại bỏ Cookies khỏi Cache Key, nhiều người dùng có thể sử dụng chung một phiên bản dữ liệu đã được cache.

Kết quả là:

- Cache Hit Ratio tăng lên đáng kể.
- Giảm số lần truy cập Origin Server.
- Website phản hồi nhanh hơn.

---

### Hỗ trợ thêm CloudFront Headers

AWS Amplify Hosting hiện hỗ trợ chuyển tiếp thêm nhiều Header từ CloudFront như:

- User-Agent
- Referer
- CloudFront-Viewer-Country
- CloudFront-Viewer-City

Điều này giúp ứng dụng:

- Cá nhân hóa nội dung.
- Xác định vị trí người dùng.
- Phân tích thiết bị truy cập.
- Hỗ trợ nhiều kịch bản xử lý phía Server.

---

### Hỗ trợ Next.js Internationalization (i18n)

Amplify Hosting hiện đã hỗ trợ tốt hơn cho các ứng dụng đa ngôn ngữ.

Thông qua Header **Accept-Language**, Next.js có thể tự động xác định ngôn ngữ mà trình duyệt của người dùng đang sử dụng và hiển thị nội dung phù hợp mà không cần cấu hình phức tạp.

---

### Brotli Compression

AWS cũng tự động bật **Brotli Compression** cho tất cả ứng dụng.

Đây là thuật toán nén hiện đại giúp:

- Giảm kích thước file HTML.
- CSS nhỏ hơn.
- JavaScript nhẹ hơn.

Nhờ đó:

- Website tải nhanh hơn.
- Giảm băng thông.
- Cải thiện điểm SEO.

---

## 3. Kết quả đạt được

AWS tiến hành Benchmark với ứng dụng **Next.js 14** và ghi nhận:

- Cải thiện khoảng **98%** thời gian phản hồi trung bình.
- Cải thiện khoảng **98%** thời gian phản hồi p95.
- Cache Hit Ratio đạt tới **99.99%** đối với Static Assets.

Ngoài ra, website tài liệu của AWS Amplify cũng duy trì Cache Hit Ratio trên **90%**, cho thấy các cải tiến mang lại hiệu quả rõ rệt trong thực tế.

---

## 4. Đánh giá theo AWS Well-Architected Framework

### Performance Efficiency

Các Cache Policy mới giúp tận dụng tối đa Amazon CloudFront để phục vụ nội dung từ Edge Location gần người dùng nhất, giảm đáng kể độ trễ khi truy cập.

### Cost Optimization

Việc tăng Cache Hit Ratio giúp giảm số lượng request phải gửi về Origin Server, từ đó giảm chi phí xử lý và băng thông.

### Reliability

CloudFront tự động phân phối nội dung trên mạng lưới Edge toàn cầu và tự động làm mới Cache sau mỗi lần triển khai ứng dụng, giúp dữ liệu luôn được cập nhật.

### Operational Excellence

Các cấu hình Cache có thể quản lý trực tiếp trên Amplify Hosting thông qua Console, CLI hoặc API, giúp việc vận hành và bảo trì trở nên đơn giản hơn.

---

## 5. Kết luận

Theo mình, đây là một trong những cải tiến đáng chú ý của AWS Amplify Hosting trong năm 2024. Chỉ với việc tối ưu Cache Policies, loại bỏ Cookies khỏi Cache Key và bổ sung các tính năng như Brotli Compression hay hỗ trợ Next.js i18n, AWS đã giúp cải thiện đáng kể hiệu năng của các ứng dụng web mà gần như không yêu cầu thay đổi mã nguồn.

Đối với các dự án React, Next.js hoặc Static Website triển khai trên Amplify Hosting, đây là những tính năng rất đáng để tận dụng nhằm tăng tốc độ tải trang, cải thiện trải nghiệm người dùng và giảm chi phí vận hành.

---

## 6. Link bài viết gốc

https://aws.amazon.com/blogs/mobile/cdn-caching-improvements-for-better-app-performance-with-aws-amplify-hosting/

---

## 7. Hướng dẫn

- Tìm hiểu cơ chế hoạt động của Amazon CloudFront và CDN Cache.
- Thực hành triển khai ứng dụng React hoặc Next.js trên AWS Amplify Hosting.
- Quan sát Cache Hit Ratio trước và sau khi loại bỏ Cookies khỏi Cache Key để đánh giá hiệu quả của tính năng mới.