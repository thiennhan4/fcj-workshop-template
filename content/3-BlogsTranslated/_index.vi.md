---
title: "Các bài blogs đã dịch"
date: 2024-01-01
weight: 3
chapter: false
pre: " <b> 3. </b> "
---

{{% notice warning %}}  
⚠️ **Lưu ý:** Các thông tin dưới đây chỉ nhằm mục đích tham khảo, vui lòng **không sao chép nguyên văn** cho bài báo cáo của bạn kể cả warning này.
{{% /notice %}}

Tại đây sẽ là phần liệt kê, giới thiệu các blogs mà các bạn đã dịch. Ví dụ:

###  [Blog 1 - Giới thiệu các kỹ năng mã nguồn mở cho các phương pháp thực hành tốt nhất của AWS SDK](3.1-Blog1/)
Blog giới thiệu bộ AWS SDK Skills thuộc AWS Agent Toolkit mã nguồn mở, giúp các tác nhân lập trình AI (coding agents) sử dụng AWS SDK đúng cách. Bài viết chỉ ra các lỗi phổ biến mà AI thường mắc phải như sinh mã không biên dịch được, bỏ qua Paginator/Waiter làm giảm hiệu suất, hay bắt exception sai kiểu gây lỗi logic khó phát hiện. Mỗi Skill gồm SKILL.md, references/ và scripts/, được đo lường hiệu quả qua các bài test thực tế trên S3, DynamoDB... Hiện có 3 skill cho Swift, JavaScript v3 và Python (Boto3), cài đặt qua lệnh npx skills add.
###  [Blog 2 -  Bảo mật .NET Microservices trên AWS với Microsoft Entra ID ](3.2-Blog2/)
Blog trình bày giải pháp bảo mật giao tiếp giữa các microservice .NET chạy trên AWS bằng cách kết hợp Microsoft Entra ID (Azure AD) với OAuth 2.0 Client Credentials Flow. Mỗi service được đăng ký như một Application riêng (có Client ID/Secret/Scope), khi gọi nhau phải xin Access Token từ Entra ID rồi gửi kèm trong header Authorization: Bearer. Bài viết nhấn mạnh các thực hành tốt: lưu Client Secret trong AWS Secrets Manager, cache Access Token để tăng hiệu năng, dùng [Authorize] trong ASP.NET Core, và đánh giá giải pháp theo 5 trụ cột của AWS Well-Architected Framework.
###  [Blog 3 -  Cải thiện hiệu suất ứng dụng với CDN Caching trong AWS Amplify Hosting ](3.3-Blog3/)
Blog nói về các cải tiến cơ chế CDN Caching trên AWS Amplify Hosting nhằm tăng tốc độ tải trang mà không cần sửa code. Điểm nổi bật là loại bỏ Cookies (tracking, session...) khỏi Cache Key giúp tăng Cache Hit Ratio, đồng thời bổ sung: Cache Policy riêng cho từng loại nội dung (static/SSR/image), hỗ trợ forward thêm CloudFront Headers, hỗ trợ Next.js i18n qua header Accept-Language, và tự động bật Brotli Compression. Kết quả benchmark trên Next.js 14 cho thấy cải thiện ~98% thời gian phản hồi và Cache Hit Ratio đạt 99.99% với static assets.
