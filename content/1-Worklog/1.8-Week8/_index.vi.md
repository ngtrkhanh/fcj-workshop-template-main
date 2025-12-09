---
title: "Worklog Tuần 8"
date: 2025-11-11
weight: 8
chapter: false
pre: " <b> 1.8. </b> "
---


### Mục tiêu tuần 8:

* Bắt đầu triển khai project thực tế sử dụng các dịch vụ serverless của AWS.
* Xây dựng backend cơ bản sử dụng DynamoDB, Lambda và API Gateway.
* Đăng ký domain và cấu hình DNS để chuẩn bị cho việc public API.

---

### Các công việc triển khai trong tuần này:

| Thứ | Công việc                                                                                                                                              | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | ------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------ | --------------- | -------------- |
| 2   | - Phân tích yêu cầu project <br>- Xác định workflow backend: API Gateway → Lambda → DynamoDB                                                          | 27/10/2025   | 27/10/2025      |  |
| 3   | - Bắt đầu tạo DynamoDB Table <br>&emsp; + Tạo bảng (Partition key) <br>&emsp; + Thêm Item dữ liệu mẫu                                                | 28/10/2025   | 28/10/2025      |  |
| 4   | - Đăng ký domain bằng Route 53 <br>&emsp; + Mua domain <br>&emsp; + Tạo Public Hosted Zone <br>&emsp; + Tạo record A/CNAME để chuẩn bị routing       | 29/10/2025   | 29/10/2025      |  |
| 5   | - Viết Lambda function cho API <br>&emsp; + Xử lý CRUD cơ bản với DynamoDB SDK <br>&emsp; + Tạo IAM Role cho Lambda                                  | 30/10/2025   | 30/10/2025      |  |
| 6   | - Tạo API Gateway & tích hợp Lambda <br>&emsp; + Tạo REST API <br>&emsp; + Tạo method GET/POST <br>&emsp; + Deploy stage <br>&emsp; + Test API       | 31/10/2025   | 31/10/2025      |  |

---

### Kết quả đạt được tuần 8:

* Hoàn thành việc **tạo DynamoDB Table** phục vụ cho project:
  * Tạo bảng với Partition Key phù hợp
  * Thêm dữ liệu mẫu để kiểm tra workflow
  * Test Query/Scan để đảm bảo tính đúng đắn

* Đăng ký thành công **domain Route 53**, bao gồm:
  * Tạo Hosted Zone
  * Tạo các bản ghi DNS cơ bản
  * Kiểm tra domain propagation

* Triển khai được **Lambda function** cho backend:
  * Code logic xử lý yêu cầu (GET, POST)
  * Tích hợp với DynamoDB thông qua SDK
  * Phân quyền chính xác bằng IAM Role

* Xây dựng và cấu hình **API Gateway**:
  * Tạo REST API + Resource + Method
  * Kết nối Lambda thông qua Lambda Proxy
  * Deploy stage (dev)
  * Test và gọi API thành công qua endpoint

* Kết nối trọn vẹn workflow:
  **Client → API Gateway → Lambda → DynamoDB**

* Hiểu rõ pipeline serverless thực tế và cách liên kết các dịch vụ lại thành backend hoàn chỉnh.

* …

