---
title: "Worklog Tuần 3"
date: "2025-09-09T19:53:52+07:00"
weight: 3
chapter: false
pre: " <b> 1.3. </b> "
---



### Mục tiêu tuần 3:

* Kết nối, làm quen với các thành viên trong First Cloud Journey.
* Hiểu dịch vụ AWS cơ bản, cách dùng console & CLI.

### Các công việc cần triển khai trong tuần này:
| Ngày    | Nhiệm vụ                                                                                                                                                                                                                              | Ngày bắt đầu | Ngày hoàn thành | Tài liệu tham khảo                                                                            |
| ------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------ | --------------- | --------------------------------------------------------------------------------------------- |
| Thứ Hai | - Kiến thức nền tảng về cơ sở dữ liệu với Amazon RDS: tìm hiểu các khái niệm cốt lõi (DB instance, loại engine, storage, Multi‑AZ, backup, security group cho DB). - Ôn lại các trường hợp sử dụng phổ biến của RDS cho ứng dụng web. | 22/09/2025   | 22/09/2025      | https://www.youtube.com/watch?v=TQFwQAre0H4&list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i&index=59  |
| Thứ Ba  | - Thực hành: tạo một RDS database instance trong cùng VPC với EC2 web server ở Tuần 2.- Cấu hình bảo mật để chỉ EC2 instance (hoặc subnet ứng dụng) mới có thể kết nối đến RDS instance.                                              | 23/09/2025   | 23/09/2025      | https://www.youtube.com/watch?v=SlP-KdSs3IM&list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i&index=225 |
| Thứ Tư  | - Mở rộng ứng dụng với EC2 Auto Scaling: tìm hiểu các khái niệm Launch Template/Configuration, Auto Scaling Group, scaling policies, health checks. - Thiết kế một chính sách scaling đơn giản dựa trên CPU utilization cho web tier. | 24/09/2025   | 24/09/2025      | https://www.youtube.com/watch?v=hFVYG8WqfU0&list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i&index=80  |
| Thứ Năm | - Thực hành: tạo một Auto Scaling Group cho các web EC2 instance trải trên ít nhất hai AZ (nếu có).- Kiểm tra hành vi scale‑out/scale‑in bằng cách điều chỉnh ngưỡng hoặc tạo tải.                                                    | 25/09/2025   | 25/09/2025      | https://000006.awsstudygroup.com                                                              |
| Thứ Sáu | - Tham gia một sự kiện AWS                                                                                                                                                                                                            | 26/09/2025   | 26/09/2025      |                                                                                               |

### Kết quả đạt được tuần 3:

* Hiểu AWS là gì và nắm được các nhóm dịch vụ cơ bản: 
  * Compute
  * Storage
  * Networking 
  * Database
  * ...

* Đã tạo và cấu hình AWS Free Tier account thành công.

* Làm quen với AWS Management Console và biết cách tìm, truy cập, sử dụng dịch vụ từ giao diện web.

* Cài đặt và cấu hình AWS CLI trên máy tính bao gồm:
  * Access Key
  * Secret Key
  * Region mặc định
  * ...

* Sử dụng AWS CLI để thực hiện các thao tác cơ bản như:

  * Kiểm tra thông tin tài khoản & cấu hình
  * Lấy danh sách region
  * Xem dịch vụ EC2
  * Tạo và quản lý key pair
  * Kiểm tra thông tin dịch vụ đang chạy
  * ...

* Có khả năng kết nối giữa giao diện web và CLI để quản lý tài nguyên AWS song song.
* ...


