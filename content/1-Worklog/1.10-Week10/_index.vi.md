---
title: "Worklog Tuần 10"
date: 2025-11-25
weight: 10
chapter: false
pre: " <b> 1.10. </b> "
---


### Mục tiêu tuần 10:

* Tìm giải pháp thay thế sau khi yêu cầu nâng cấp SES ra khỏi sandbox bị từ chối.  
* Chuyển sang sử dụng **Resend** để gửi email trong hệ thống.  
* Cấu hình **API Authentication** (JWT/Auth Token/API Key) để bảo vệ API.  
* Hoàn thiện lại flow gửi mail qua API sau khi chuyển sang Resend.

---

### Các công việc triển khai trong tuần này:

| Thứ | Công việc                                                                                                                                                    | Bắt đầu     | Hoàn thành  | Nguồn |
| --- | ------------------------------------------------------------------------------------------------------------------------------------------------------------ | ----------- | ----------- | ----- |
| 2   | - Nhận thông báo SES bị từ chối rời Sandbox <br> - Đánh giá lại yêu cầu gửi email của project và tìm dịch vụ thay thế                                       | 10/11/2025  | 10/11/2025  | |
| 3   | - Nghiên cứu Resend: <br>&emsp; + Cách tạo API Key <br>&emsp; + Cách verify domain <br>&emsp; + Các API gửi mail                                           | 11/11/2025  | 11/11/2025  | https://resend.com/docs |
| 4   | - Tích hợp Resend vào Lambda: <br>&emsp; + Sử dụng Resend SDK/HTTP API <br>&emsp; + Tạo template email <br>&emsp; + Test gửi mail                           | 12/11/2025  | 12/11/2025  |  |
| 5   | - Cấu hình Authentication cho API: <br>&emsp; + API Key hoặc <br>&emsp; + JWT với Cognito (tùy chọn kịch bản) <br>&emsp; + Enable Auth trên API Gateway    | 13/11/2025  | 13/11/2025  |  |
| 6   | - Test End-to-End: <br>&emsp; + Client gửi request → API Gateway → Lambda → Resend <br>&emsp; + Kiểm tra token/Auth <br>&emsp; + Log và fix lỗi phát sinh | 14/11/2025  | 14/11/2025  |  |

---

### Kết quả đạt được tuần 10:

* **SES bị từ chối nâng cấp khỏi Sandbox**, dẫn đến:
  * Không gửi mail được tới email không verify
  * Không phù hợp cho môi trường production
  * Cần tìm phương án gửi mail bên thứ 3

* Chuyển sang sử dụng **Resend**:
  * Tạo tài khoản và API Key
  * Verify domain để cải thiện deliverability
  * Gửi email thành công qua Resend API

* Tích hợp hoàn thiện **Resend + Lambda**:
  * Gửi mail HTML template
  * Gửi mail OTP/verification/notification
  * Mã hóa API Key bằng AWS Secrets Manager (tùy chọn)

* Thiết lập **Authentication cho API Gateway**:
  * Sử dụng API Key / hoặc JWT Auth qua Cognito
  * Yêu cầu token khi gọi API gửi email
  * Tăng bảo mật cho hệ thống

* Test toàn bộ workflow mới:
  **Client → Authenticated API Gateway → Lambda → Resend → Email Delivered**

* Nắm rõ cách triển khai email service ngoài AWS khi SES bị hạn chế.

* …
