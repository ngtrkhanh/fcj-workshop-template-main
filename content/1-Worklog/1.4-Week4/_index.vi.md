---
title: "Worklog Tuần 4"
date: "2025-09-09T19:53:52+07:00"
weight: 4
chapter: false
pre: " <b> 1.4. </b> "
---


### Mục tiêu tuần 4:

* Kết nối, làm quen với các thành viên trong First Cloud Journey.
* Hiểu dịch vụ AWS cơ bản, cách dùng console & CLI.

### Các công việc cần triển khai trong tuần này:
| Ngày    | Nhiệm vụ                                                                                                                                                                                                                                                                                                       | Ngày bắt đầu | Ngày hoàn thành | Tài liệu tham khảo                                                                                                                                                               |
| ------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------ | --------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Thứ Hai | - Thiết lập Hybrid DNS với Route 53 Resolver: tìm hiểu các khái niệm cơ bản về Route 53, Route 53 Resolver, hybrid DNS giữa on‑prem và AWS, inbound/outbound endpoint và Resolver rule (mức giới thiệu).- Ghi chú lại các trường hợp sử dụng hybrid DNS điển hình trong môi trường doanh nghiệp.               | 06/10/2025   | 06/10/2025      | https://www.youtube.com/watch?v=FGicpWOmMDI&list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i&index=46youtube​                                                                             |
| Thứ Ba  | - Thực hiện theo lab Hybrid DNS: tạo các VPC, subnet cần thiết và cấu hình Route 53 ban đầu cho kịch bản lab.- Vẽ một sơ đồ kiến trúc nhỏ thể hiện DNS on‑prem, các inbound/outbound endpoint của Route 53 Resolver và các VPC.                                                                                | 07/10/2025   | 07/10/2025      | https://000010.awsstudygroup.com/vi/                                                                                                                                             |
| Thứ Tư  | - Cấu hình Security Group cho lab Hybrid DNS: chỉ giữ lại các port ICMP (ping) và RDP cần cho việc kiểm thử, loại bỏ các port không dùng để tuân thủ nguyên tắc least‑privilege và tăng cường bảo mật.- Kiểm tra kết nối (ping, RDP) để đảm bảo các rule của Security Group hoạt động như mong đợi.            | 08/10/2025   | 08/10/2025      | https://www.youtube.com/watch?v=kE_krznNBFU&list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i&index=49youtube                                                                              |
| Thứ Năm | - Hoàn tất Hybrid DNS với Route 53 Resolver: cấu hình inbound và outbound Resolver endpoint và tạo các Resolver rule để forward các tên miền cụ thể giữa on‑prem và AWS.- Kiểm tra phân giải DNS theo cả hai chiều (từ “on‑prem” lên AWS và từ AWS về lại on‑prem).                                            | 09/10/2025   | 09/10/2025      | https://www.youtube.com/watch?v=L-2YfZceoAU&list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i&index=61000003.awsstudygroup                                                                 |
| Thứ Sáu | - Thiết lập AWS Transit Gateway: tìm hiểu các khái niệm và chi phí (attachment, xử lý dữ liệu) và tạo một Transit Gateway trong tài khoản lab.- Gắn các VPC hiện có vào Transit Gateway và cập nhật bảng định tuyến của VPC để lưu lượng giữa các VPC đi qua TGW; kiểm tra khả năng kết nối chéo giữa các VPC. | 10/10/2025   | 10/10/2025      | https://www.youtube.com/watch?v=W1m_OFPDui0&list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i&index=68 https://www.youtube.com/watch?v=QSXgL2KodQI&list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i |


### Kết quả đạt được tuần 4:

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


