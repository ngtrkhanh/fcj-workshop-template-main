---
title: "Worklog Tuần 7"
date: "2025-09-09T19:53:52+07:00"
weight: 1
chapter: false
pre: " <b> 1.7. </b> "
---
{{% notice warning %}}
⚠️ **Lưu ý:** Các thông tin dưới đây chỉ nhằm mục đích tham khảo, vui lòng **không sao chép nguyên văn** cho bài báo cáo của bạn kể cả warning này.
{{% /notice %}}


### Mục tiêu tuần 7:

* Học khái niệm serverless với AWS Lambda.
* Tạo và kiểm thử Lambda function đơn giản.
* Expose Lambda thông qua API Gateway.
* Test API bằng các công cụ như Postman.

### Các công việc cần triển khai trong tuần này:
| Thứ | Công việc                                                                                                                                                                                   | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu                            |
| --- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------ | --------------- | ----------------------------------------- |
| 2   | - Tìm hiểu tổng quan về serverless và AWS Lambda: khi nào nên dùng Lambda, pricing, giới hạn                                                         | 20/10/2025   | 20/10/2025      | <https://docs.aws.amazon.com/lambda/latest/dg/welcome.html> |
| 3   | - Tạo Lambda function đơn giản (Hello World / JSON response) <br> - Test function trực tiếp trên AWS Console                                         | 21/10/2025   | 21/10/2025      | <> |
| 4   | - Cấu hình environment variables và IAM execution role cơ bản cho Lambda                                                                             | 22/10/2025   | 22/10/2025      | <https://docs.aws.amazon.com/lambda/latest/dg/lambda-intro-execution-role.html> |
| 5   | - Tạo API Gateway (HTTP/REST) và tích hợp với Lambda                                                                                                | 23/10/2025   | 23/10/2025      | <https://docs.aws.amazon.com/apigateway/latest/developerguide/welcome.html> |
| 6   | - Deploy API lên stage và lấy invoke URL <br> - Test API bằng Postman (kiểm tra method, status code, payload)                                       | 24/10/2025   | 24/10/2025      | <> |


### Kết quả đạt được tuần 7:

* Học các khái niệm cốt lõi của AWS Lambda:
  * Event-driven compute
  * Mô hình thực thi stateless
  * Handler function và runtime configuration

* Tạo Lambda function đơn giản trả về JSON và kiểm thử trực tiếp trên AWS Console.

* Tích hợp Lambda với API Gateway:
  * Tạo API (HTTP/REST) và cấu hình method gọi tới Lambda
  * Deploy API lên một stage và lấy invoke URL

* Test endpoint bằng Postman:
  * Gửi request HTTP và kiểm tra status code, payload trả về
  * Xác minh Lambda được invoke chính xác thông qua CloudWatch Logs


