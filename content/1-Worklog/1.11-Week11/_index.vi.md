---
title: "Worklog Tuần 11"
date: 2025-12-02
weight: 11
chapter: false
pre: " <b> 1.11. </b> "
---
{{% notice warning %}}
⚠️ **Lưu ý:** Nội dung dưới đây chỉ mang tính tham khảo. Vui lòng **không sao chép nguyên văn** vào báo cáo.
{{% /notice %}}

### Mục tiêu tuần 11:

* Tích hợp frontend với backend qua **AWS Amplify**.  
* Sử dụng **Cognito** để quản lý authentication cho frontend (login, JWT, API Key).  
* Tích hợp Lambda + Resend + API Gateway vào frontend thông qua Amplify API.  
* Triển khai CI/CD tự động qua **Amplify Console**.

---

### Các công việc triển khai trong tuần này:

| Thứ | Công việc                                                                                                                                                                 | Bắt đầu     | Hoàn thành  | Nguồn |
| --- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------- | ----------- | ----- |
| 2   | - Cấu hình Amplify project <br>&emsp; + `amplify init` <br>&emsp; + Kết nối frontend React/Vue/Angular <br>&emsp; + Tạo Amplify Auth (Cognito User Pool)                 | 17/11/2025  | 17/11/2025  | AWS Amplify Docs |
| 3   | - Tích hợp API Lambda + Resend qua **Amplify API** <br>&emsp; + Tạo GraphQL/REST endpoint <br>&emsp; + Cấu hình authentication bằng Cognito JWT/API Key                   | 18/11/2025  | 18/11/2025  | Amplify Docs, Cognito Docs |
| 4   | - Test frontend → Amplify API → Lambda → Resend <br>&emsp; + Đăng nhập Cognito thành công <br>&emsp; + Gửi email OTP/notification từ frontend                             | 19/11/2025  | 19/11/2025  | Project Docs |
| 5   | - Triển khai CI/CD trên **Amplify Console** <br>&emsp; + Kết nối repo GitHub/GitLab/CodeCommit <br>&emsp; + Tự động build & deploy frontend + backend Lambda             | 20/11/2025  | 20/11/2025  | Amplify Console Docs |
| 6   | - Test end-to-end pipeline <br>&emsp; + Push code → Amplify tự động deploy <br>&emsp; + Kiểm tra frontend hiển thị, API authentication & gửi email qua Resend            | 21/11/2025  | 21/11/2025  | CloudWatch Logs |

---

### Kết quả đạt được tuần 11:

* Tích hợp **frontend với backend** qua **Amplify** hoàn chỉnh:
  * Gọi API Lambda + Resend từ frontend
  * Xác thực Cognito (login, JWT, API Key) hoạt động
  * Flow gửi email OTP/verification/notification thành công

* Triển khai **CI/CD tự động với Amplify Console**:
  * Repo GitHub/GitLab/CodeCommit làm source
  * Amplify tự động build và deploy frontend + backend
  * Tự động update production khi push code

* Test toàn bộ workflow end-to-end:
  **Frontend → Cognito Auth → Amplify API → Lambda → Resend → Email → Frontend hiển thị thông báo**

* Hiểu rõ cách **tích hợp serverless full-stack với Amplify + Cognito + Lambda + Resend** và CI/CD.

* …
