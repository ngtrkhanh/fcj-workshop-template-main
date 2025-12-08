---
title: "Worklog Tuần 11"
date: "2025-09-09T19:53:52+07:00"
weight: 2
chapter: false
pre: " <b> 1.11. </b> "
---
{{% notice warning %}}
⚠️ **Lưu ý:** Các thông tin dưới đây chỉ nhằm mục đích tham khảo, vui lòng **không sao chép nguyên văn** cho bài báo cáo của bạn kể cả warning này.
{{% /notice %}}


### Mục tiêu tuần 11:

* Thiết kế và xây dựng mini project nhỏ trên AWS.
* Kết hợp nhiều dịch vụ như VPC, EC2, S3, RDS.
* Kiểm thử chức năng end-to-end của hệ thống.

### Các công việc cần triển khai trong tuần này:
| Thứ | Công việc                                                                                                                                                                                   | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu                            |
| --- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------ | --------------- | ----------------------------------------- |
| 2   | - Thiết kế kiến trúc tổng thể cho mini project (VPC, subnet, EC2, S3, RDS)                                                                           | 17/11/2025   | 17/11/2025      | <> |
| 3   | - Tạo mới hoặc tái sử dụng VPC với các subnet và Security Groups cần thiết                                                                           | 18/11/2025   | 18/11/2025      | <> |
| 4   | - Tạo EC2 instances cho tầng ứng dụng và cấu hình Security Groups                                                                                    | 19/11/2025   | 19/11/2025      | <> |
| 5   | - Cấu hình RDS database và kết nối với EC2 application instances                                                                                     | 20/11/2025   | 20/11/2025      | <> |
| 6   | - Sử dụng S3 để lưu trữ/serve static files cho project (nếu có)                                                                                      | 21/11/2025   | 21/11/2025      | <> |


### Kết quả đạt được tuần 11:

* Thiết kế và xây dựng mini project nhỏ trên AWS bao gồm:
  * VPC với các subnet và cấu hình mạng phù hợp
  * EC2 instances cho tầng ứng dụng
  * S3 để lưu trữ/serve static files
  * RDS làm cơ sở dữ liệu quan hệ được quản lý

* Kết nối các thành phần:
  * EC2 kết nối tới RDS để lưu trữ và truy vấn dữ liệu
  * S3 dùng để phục vụ hoặc lưu static assets

* Kiểm thử luồng end-to-end:
  * Kiểm tra kết nối giữa EC2 và RDS
  * Thực hiện đọc/ghi dữ liệu vào database
  * Truy cập nội dung tĩnh (nếu có)

* Tài liệu hóa kiến trúc mini project và các quyết định thiết kế chính.


