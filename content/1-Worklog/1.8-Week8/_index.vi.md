---
title: "Worklog Tuần 8"
date: "2025-09-09T19:53:52+07:00"
weight: 1
chapter: false
pre: " <b> 1.8. </b> "
---
{{% notice warning %}}
⚠️ **Lưu ý:** Các thông tin dưới đây chỉ nhằm mục đích tham khảo, vui lòng **không sao chép nguyên văn** cho bài báo cáo của bạn kể cả warning này.
{{% /notice %}}


### Mục tiêu tuần 8:

* Học về Amazon CloudWatch: metrics, alarms và logs.
* Hiểu cách monitor các tài nguyên AWS như EC2, RDS.
* Tạo CloudWatch alarms và notifications cơ bản.
* Khám phá CloudWatch Logs để troubleshoot và phân tích.

### Các công việc cần triển khai trong tuần này:
| Thứ | Công việc                                                                                                                                                                                   | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu                            |
| --- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------ | --------------- | ----------------------------------------- |
| 2   | - Học khái niệm CloudWatch: metrics, namespace, dimensions, alarms, logs                                                                             | 27/10/2025   | 27/10/2025      | <https://docs.aws.amazon.com/AmazonCloudWatch/latest/monitoring/WhatIsCloudWatch.html> |
| 3   | - Xem metrics của EC2 và RDS trong CloudWatch console <br> - Thực hành thay đổi khoảng thời gian, kiểu thống kê (Average, Maximum, …)               | 28/10/2025   | 28/10/2025      | <> |
| 4   | - Tạo CloudWatch alarm cơ bản (ví dụ CPUUtilization > ngưỡng) <br> - Cấu hình hành động đơn giản                                                     | 29/10/2025   | 29/10/2025      | <https://docs.aws.amazon.com/AmazonCloudWatch/latest/monitoring/AlarmThatSendsEmail.html> |
| 5   | - Khám phá CloudWatch Logs: <br>&emsp; + Mở log group của Lambda/EC2 <br>&emsp; + Filter và search log events                                        | 30/10/2025   | 30/10/2025      | <https://docs.aws.amazon.com/AmazonCloudWatch/latest/logs/WhatIsCloudWatchLogs.html> |
| 6   | - (Tuỳ chọn) Kết nối alarm với SNS để gửi notification và test gửi cảnh báo                                                                         | 31/10/2025   | 31/10/2025      | <> |


### Kết quả đạt được tuần 8:

* Xem các CloudWatch metrics cho các dịch vụ quan trọng (EC2, RDS, Lambda…) và học cách đọc biểu đồ theo mốc thời gian.

* Tạo các CloudWatch alarms cơ bản (ví dụ CPUUtilization) và cấu hình hành động thông báo đơn giản.

* Khám phá CloudWatch Logs:
  * Xem và filter log của Lambda, EC2
  * Tìm kiếm log theo pattern để xử lý lỗi

* Hiểu rõ hơn vai trò của CloudWatch trong việc giám sát sức khỏe hệ thống và phản ứng với các vấn đề hiệu năng/sẵn sàng.


