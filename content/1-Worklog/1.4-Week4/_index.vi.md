---
title: "Worklog Tuần 4"
date: "2025-09-09T19:53:52+07:00"
weight: 1
chapter: false
pre: " <b> 1.4. </b> "
---
{{% notice warning %}}
⚠️ **Lưu ý:** Các thông tin dưới đây chỉ nhằm mục đích tham khảo, vui lòng **không sao chép nguyên văn** cho bài báo cáo của bạn kể cả warning này.
{{% /notice %}}


### Mục tiêu tuần 4:

* Làm quen với khái niệm cơ sở dữ liệu quản lý (managed database) trên Amazon RDS.
* Tạo và cấu hình RDS MySQL instance.
* Kết nối EC2 tới RDS một cách an toàn.
* Hiểu và thực hành các tính năng backup, snapshot của RDS.

### Các công việc cần triển khai trong tuần này:
| Thứ | Công việc                                                                                                                                                                                   | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu                            |
| --- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------ | --------------- | ----------------------------------------- |
| 2   | - Tìm hiểu khái niệm RDS: <br>&emsp; + Amazon RDS là gì? <br>&emsp; + Các engine hỗ trợ (MySQL, PostgreSQL, …) <br>&emsp; + So sánh RDS và database tự quản lý trên EC2 <br>&emsp; + Single-AZ vs Multi-AZ | 29/09/2025   | 29/09/2025      | <https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/Welcome.html> |
| 3   | - Ôn lại các yêu cầu networking cho RDS: <br>&emsp; + DB subnet groups <br>&emsp; + Security Groups cho RDS và EC2 <br>&emsp; + Các lưu ý về VPC                                            | 30/09/2025   | 30/09/2025      | <https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/USER_VPC.html> |
| 4   | - Tạo RDS MySQL instance: <br>&emsp; + Chọn instance class và storage <br>&emsp; + Cấu hình thông tin database ban đầu <br>&emsp; + Thiết lập backup window và retention                    | 01/10/2025   | 01/10/2025      | <https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/USER_CreateDBInstance.html> |
| 5   | - Cấu hình Security Groups và networking để EC2 kết nối được tới RDS <br> - Test kết nối từ EC2 tới RDS bằng MySQL client <br> - Thực hiện các câu lệnh CRUD đơn giản                      | 02/10/2025   | 02/10/2025      | <https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/USER_ConnectToInstance.html> |
| 6   | - Khám phá các tính năng backup của RDS: <br>&emsp; + Automated backups <br>&emsp; + Manual snapshots <br>&emsp; + Tổng quan point-in-time recovery                                         | 03/10/2025   | 03/10/2025      | <https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/USER_WorkingWithAutomatedBackups.html> |


### Kết quả đạt được tuần 4:

* Tạo thành công RDS MySQL instance với cấu hình phù hợp về instance class, storage và bảo mật.

* Cấu hình Security Groups và networking để EC2 có thể kết nối an toàn tới RDS endpoint.

* Kết nối EC2 tới RDS bằng MySQL client, chạy thử các câu lệnh CRUD cơ bản trên database.

* Thực hành các tính năng backup của RDS:
  * Automated backups và cấu hình thời gian giữ backup
  * Tạo snapshot thủ công
  * Khôi phục RDS instance từ snapshot để kiểm tra khả năng phục hồi

* Ghi chép lại các khái niệm quan trọng về RDS:
  * Triển khai Single-AZ vs Multi-AZ
  * Lựa chọn storage và các yếu tố hiệu năng
  * Mô hình kết nối giữa tầng ứng dụng và RDS


