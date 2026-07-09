---
title: "Blog 1"
date: 08-07-2026
weight: 1
chapter: false
pre: " <b> 3.1. </b> "
---

# Giới thiệu các kỹ năng mã nguồn mở cho các phương pháp thực hành tốt nhất của AWS SDK

Chúng tôi đã phát hành một bộ Kỹ năng AWS SDK như một phần của Bộ công cụ tác nhân mã nguồn mở dành cho AWS . Đây là những kỹ năng trí tuệ nhân tạo giúp các tác nhân lập trình biết cách tuân thủ các thực tiễn tốt nhất của AWS SDK. Dự án này có sẵn trên GitHub theo giấy phép Apache-2.0.

---

## 1 Vấn đề

Các tác nhân lập trình AI nắm được cấu trúc tổng quát của việc sử dụng AWS SDK, nhưng lại mắc lỗi ở các chi tiết. Chúng tạo ra tên API không chính xác, sử dụng kiểu tham số không chính xác và bỏ sót các mẫu cụ thể của SDK như bộ phân trang, trình chờ và các API cấp cao như trình quản lý truyền tải cho Amazon Simple Storage Service (Amazon S3). Những lỗi này đặc biệt phổ biến đối với các SDK mới hơn như AWS SDK for Swift , nơi các tác nhân tạo ra mã trông có vẻ hợp lý nhưng lại không biên dịch được.

Khi các nhà phát triển ngày càng dựa vào các tác nhân AI để viết mã AWS SDK, chúng ta cần đảm bảo rằng các tác nhân đó tạo ra mã có thể biên dịch, tuân thủ các thực tiễn tốt nhất và sử dụng từng SDK theo đúng cách mà nó được thiết kế.

## 2. Cần có những kỹ năng gì?

Kỹ năng (**Skills**) là các gói mô-đun cung cấp cho các tác nhân lập trình AI kiến thức chuyên biệt về SDK. Mỗi kỹ năng được xây dựng bởi đội ngũ phát triển SDK của ngôn ngữ tương ứng, phản ánh những lỗi mà các tác nhân AI thường gặp khi làm việc với SDK đó.

Một kỹ năng thường bao gồm:

- **`SKILL.md`**
  - Chứa các hướng dẫn cốt lõi.
  - Bao gồm các mẫu sử dụng SDK.
  - Cung cấp các ví dụ minh họa cụ thể.

- **`references/`**
  - Chứa tài liệu tham khảo về các chủ đề chuyên sâu.
  - Chỉ được tải khi cần thiết.

- **`scripts/`**
  - Chứa các tập lệnh dùng để tự động hóa quá trình:
    - Build
    - Test
    - Validation

Các kỹ năng được thiết kế độc lập với tác nhân lập trình, vì vậy chúng có thể hoạt động với bất kỳ tác nhân AI nào hỗ trợ định dạng **Open Skill Format**.
## 3. Các kỹ năng giúp ngăn ngừa những lỗi thường gặp

Các kỹ năng (Skills) được thiết kế để giúp tác nhân AI tránh các lỗi phổ biến khi làm việc với AWS SDK, từ lỗi biên dịch đến các vấn đề về hiệu suất và xử lý ngoại lệ.

### 3.1. Mã không biên dịch được

Đây là lỗi phổ biến nhất khi sử dụng các SDK mới, do dữ liệu huấn luyện của tác nhân AI còn hạn chế hoặc đã lỗi thời.

Ví dụ, với **AWS SDK for Swift**, nhiều tác nhân AI thường tạo ra đoạn mã sau:

```swift
// What agents tend to write. Does not compile.
let client = S3Client()
let response = client.listBuckets(input: ListBucketsInput())
```

Đoạn mã trên không thể biên dịch vì:

- `S3Client()` là hàm khởi tạo `async throws`.
- `listBuckets()` cũng là hàm `async throws`.

Sau khi cài đặt kỹ năng dành cho Swift, tác nhân sẽ sinh mã đúng:

```swift
let config = try await S3Client.S3ClientConfig(region: "us-west-2")
let client = S3Client(config: config)
let response = try await client.listBuckets(input: ListBucketsInput())
```

Nhờ đó, mã nguồn có thể biên dịch và hoạt động chính xác ngay từ lần đầu.

---

### 3.2. Mã chạy được nhưng hiệu suất kém

Một số tác nhân AI tạo ra mã có thể chạy nhưng không tận dụng các tính năng tối ưu của AWS SDK, chẳng hạn như:

- Không sử dụng **Paginator** cho các API như `ListObjects`.
- Không sử dụng **Waiter** để theo dõi trạng thái tài nguyên.
- Không sử dụng các phương thức cấp cao như:
  - `upload_file`
  - `download_file`

Hậu quả có thể bao gồm:

- Chỉ lấy được dữ liệu của trang đầu tiên.
- Gửi quá nhiều lệnh gọi API không cần thiết.
- Bỏ qua cơ chế tải lên nhiều phần (Multipart Upload).
- Hiệu suất thấp khi xử lý dữ liệu lớn.

Khi kỹ năng được cài đặt, tác nhân AI sẽ tự động sử dụng đúng các tính năng của SDK để tối ưu hiệu năng và chi phí.

---

### 3.3. Mã chạy được nhưng có lỗi khó phát hiện

Một số lỗi nhỏ rất khó nhận biết có thể xảy ra, ví dụ:

- Tự chuyển đổi kiểu dữ liệu của DynamoDB như:

```json
{"S": "value"}
```

- Bắt ngoại lệ quá chung (`Exception`) thay vì sử dụng ngoại lệ cụ thể như:

```text
ConditionalCheckFailedException
```

Sau khi cài đặt kỹ năng, tác nhân AI sẽ:

- Sử dụng **Document Client** để tự động chuyển đổi dữ liệu.
- Bắt đúng kiểu ngoại lệ tương ứng với từng API.
- Giảm đáng kể các lỗi logic khó phát hiện.

---

## 4. Đo lường hiệu quả

Mỗi kỹ năng được đánh giá thông qua bộ kiểm thử gồm nhiều tác vụ thực tế như:

- Thao tác với Amazon S3.
- Truy vấn Amazon DynamoDB.
- Cấu hình máy khách.
- Tạo URL ký trước (Presigned URL).
- Quản lý thông tin xác thực.

Mã nguồn được đánh giá dựa trên các tiêu chí:

- Có biên dịch thành công hay không.
- Có vượt qua kiểm tra cú pháp (Lint) hay không.
- Có thực hiện đúng yêu cầu của bài toán hay không.

Mỗi bài kiểm thử được thực hiện hai lần:

1. Không cài đặt kỹ năng.
2. Có cài đặt kỹ năng.

Kết quả cho thấy mã được tạo khi có kỹ năng luôn vượt qua nhiều bài kiểm thử hơn và có chất lượng cao hơn.

---

## 5. Các kỹ năng hiện có

| Kỹ năng | SDK | Nội dung |
|---------|-----|----------|
| `aws-sdk-swift-usage` | AWS SDK for Swift | Mẫu lập trình bất đồng bộ, cấu hình máy khách, khởi tạo Client |
| `aws-sdk-js-v3-usage` | AWS SDK for JavaScript v3 | Cấu trúc gói, Client, Middleware, Runtime Authentication |
| `aws-sdk-python-usage` | Boto3 / Botocore | Client, Resource, Paginator, Waiter và xử lý ngoại lệ |

---

## 6. Bắt đầu sử dụng

Để cài đặt một kỹ năng từ **AWS Agent Toolkit**, sử dụng lệnh:

```bash
npx skills add aws/agent-toolkit-for-aws/skills --skill <skill>
```

Thay `<skill>` bằng tên kỹ năng mong muốn, ví dụ:

- `aws-sdk-swift-usage`
- `aws-sdk-js-v3-usage`
- `aws-sdk-python-usage`

Có thể sử dụng tham số `--skill` nhiều lần để cài đặt đồng thời nhiều kỹ năng.

## 7. Bài học chính
Qua bài viết có thể rút ra một số bài học quan trọng:

- Các tác nhân AI cần được bổ sung kiến thức chuyên biệt thông qua **Skills** để sử dụng AWS SDK một cách chính xác.
- Skills giúp giảm đáng kể các lỗi biên dịch, lỗi logic và các vấn đề về hiệu suất khi sinh mã.
- Việc tận dụng các tính năng sẵn có của AWS SDK như **Paginator**, **Waiter** và **Document Client** giúp mã nguồn tuân theo các thực hành tốt nhất.
- Sử dụng Skills giúp lập trình viên tiết kiệm thời gian sửa lỗi và nâng cao chất lượng mã nguồn được tạo bởi AI.

## 8. Ứng dụng
Skills có thể được ứng dụng trong nhiều tình huống phát triển phần mềm, bao gồm:

- Hỗ trợ các tác nhân AI sinh mã chính xác khi làm việc với AWS SDK.
- Phát triển các ứng dụng sử dụng Amazon S3, Amazon DynamoDB và các dịch vụ AWS khác.
- Hỗ trợ lập trình viên mới nhanh chóng làm quen với các SDK của AWS.
- Tăng năng suất phát triển phần mềm và giảm chi phí bảo trì mã nguồn.
- Áp dụng trong các công cụ hỗ trợ lập trình sử dụng AI như Amazon Q Developer, GitHub Copilot và các Coding Agent hỗ trợ định dạng Open Skill.
## 9. Kết luận

- Các kỹ năng (Skills) đóng vai trò quan trọng trong việc nâng cao chất lượng mã nguồn do các tác nhân AI tạo ra khi sử dụng AWS SDK. Bằng cách cung cấp các hướng dẫn, ví dụ thực tế và phương pháp triển khai tối ưu, các kỹ năng giúp giảm thiểu lỗi biên dịch, cải thiện hiệu suất thực thi và hạn chế những lỗi logic khó phát hiện.
- Bên cạnh đó, việc áp dụng các kỹ năng còn giúp tác nhân AI tận dụng đúng các tính năng của AWS SDK như Paginator, Waiter, Document Client và các phương thức truyền tải cấp cao, từ đó tạo ra mã nguồn chính xác, hiệu quả và tuân theo các thực hành tốt nhất.
- Nhìn chung, việc cài đặt và sử dụng Skills là một bước quan trọng giúp các tác nhân AI hỗ trợ lập trình viên phát triển ứng dụng trên AWS nhanh hơn, đáng tin cậy hơn và giảm đáng kể thời gian chỉnh sửa mã sau khi sinh tự động.