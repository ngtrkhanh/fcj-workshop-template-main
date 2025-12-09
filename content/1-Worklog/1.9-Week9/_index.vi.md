---
title: "Worklog Tuần 9"
date: 2025-11-18
weight: 9
chapter: false
pre: " <b> 1.9. </b> "
---
{{% notice warning %}}
⚠️ **Lưu ý:** Các thông tin dưới đây chỉ nhằm mục đích tham khảo. Vui lòng **không sao chép nguyên văn** cho bài báo cáo của bạn, bao gồm cả dòng cảnh báo này.
{{% /notice %}}

### Mục tiêu tuần 9:

* Tích hợp Google Authentication vào Amazon Cognito để cho phép người dùng đăng nhập bằng Google.
* Cấu hình dịch vụ Amazon SES để gửi email (notification, verification, OTP…).
* Kiểm tra end-to-end flow: user login → Cognito → nhận email từ SES.

---

### Các công việc triển khai trong tuần này:

| Thứ | Công việc                                                                                                                                                       | Bắt đầu | Hoàn thành | Nguồn |
| --- | --------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------- | ---------- | ------ |
| 2   | - Chuẩn bị môi trường Cognito <br> - Tạo User Pool & App Client mới cho Google Login                                                                           | 03/11/2025 | 03/11/2025 |  |
| 3   | - Cấu hình Google OAuth: <br>&emsp; + Tạo OAuth Client ID trong Google Cloud Platform <br>&emsp; + Lấy Client ID & Client Secret                                | 04/11/2025 | 04/11/2025 |  |
| 4   | - Tích hợp Google vào Cognito: <br>&emsp; + Tạo Identity Provider (IdP) Google <br>&emsp; + Mapping attributes (email, name) <br>&emsp; + Kiểm tra login flow | 05/11/2025 | 05/11/2025 |  |
| 5   | - Thiết lập Amazon SES: <br>&emsp; + Verify domain <br>&emsp; + Verify email sender <br>&emsp; + Cấu hình DKIM <br>&emsp; + Chuyển SES ra khỏi Sandbox          | 06/11/2025 | 06/11/2025 |  |
| 6   | - Tạo Lambda gửi mail qua SES <br>&emsp; + Tích hợp API Gateway để gửi mail <br>&emsp; + Test gửi email qua REST API                                           | 07/11/2025 | 07/11/2025 |  |

---

### Kết quả đạt được tuần 9:

* Tích hợp thành công **Google Login** vào Amazon Cognito:
  * Tạo User Pool + App Client
  * Tạo Google OAuth Credential trên GCP
  * Liên kết Google IdP vào Cognito
  * Đăng nhập bằng Google thành công và nhận được token từ Cognito

* Cấu hình hoàn chỉnh **Amazon SES**:
  * Verify domain + email
  * Enable DKIM để tăng độ tin cậy email
  * Gửi email thành công sau khi rời khỏi SES Sandbox

* Viết Lambda để **gửi email tự động qua SES**:
  * Hỗ trợ gửi email thông báo / OTP / verification
  * Tích hợp API Gateway để gửi mail qua HTTP request

* Kiểm tra toàn bộ workflow:
  **Login bằng Google → Cognito xác thực → Lambda xử lý → SES gửi email**

* Hiểu rõ quy trình tích hợp OAuth bên thứ 3 & thiết lập email service trong AWS.

* …
