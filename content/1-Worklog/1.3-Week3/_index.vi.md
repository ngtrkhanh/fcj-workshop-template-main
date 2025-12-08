---
title: "Worklog Tuần 3"
date: "2025-09-09T19:53:52+07:00"
weight: 1
chapter: false
pre: " <b> 1.3. </b> "
---
{{% notice warning %}}
⚠️ **Lưu ý:** Các thông tin dưới đây chỉ nhằm mục đích tham khảo, vui lòng **không sao chép nguyên văn** cho bài báo cáo của bạn kể cả warning này.
{{% /notice %}}


### Mục tiêu tuần 3:

* Học các khái niệm và triển khai Auto Scaling.
* Cấu hình Auto Scaling Groups để quản lý instances tự động.
* Tích hợp Auto Scaling với Load Balancer để đảm bảo high availability.
* Hiểu và triển khai Elastic IP addresses.
* Thiết lập SNS notifications cho các sự kiện Auto Scaling.
* Viết tài liệu giải thích các khái niệm AWS High Availability & Scaling.

### Các công việc cần triển khai trong tuần này:
| Thứ | Công việc                                                                                                                                                                                   | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu                            |
| --- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------ | --------------- | ----------------------------------------- |
| 2   | - Học các khái niệm Auto Scaling: <br>&emsp; + Launch Templates <br>&emsp; + Auto Scaling Groups (ASG) <br>&emsp; + Scaling policies <br>&emsp; + Min/Max/Desired capacity <br>&emsp; + Health checks | 09/22/2025   | 09/22/2025      | <https://docs.aws.amazon.com/autoscaling/ec2/userguide/what-is-amazon-ec2-auto-scaling.html> |
| 3   | - Tạo Launch Template cho EC2 instances <br> - Cấu hình Launch Template với AMI, instance type, security groups <br> - Cấu hình user data scripts nếu cần <br> - Kiểm tra Launch Template bằng cách launch instance | 09/23/2025   | 09/23/2025      | <https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/ec2-launch-templates.html> |
| 4   | - Tạo Auto Scaling Group (ASG) <br> - Cấu hình ASG với min/max/desired capacity <br> - Gắn Launch Template vào ASG <br> - Cấu hình ASG sử dụng nhiều Availability Zones <br> - Tích hợp ASG với ALB Target Group hiện có | 09/24/2025   | 09/24/2025      | <https://docs.aws.amazon.com/autoscaling/ec2/userguide/auto-scaling-groups.html> |
| 5   | - Tạo CloudWatch alarms cho CPU utilization <br> - Cấu hình scale-out policy: Thêm instances khi CPU > 50% <br> - Cấu hình scale-in policy: Xóa instances khi CPU giảm <br> - Kiểm tra scale-out bằng cách tạo CPU load | 09/25/2025   | 09/25/2025      | <https://docs.aws.amazon.com/autoscaling/ec2/userguide/as-scaling-simple-step.html> |
| 6   | - Kiểm tra hành vi scale-in khi CPU load giảm <br> - Xác minh tích hợp ASG với ALB cho high availability <br> - Giám sát các hoạt động Auto Scaling và instance lifecycle <br> - Tìm hiểu về Elastic IP (EIP) | 09/26/2025   | 09/26/2025      | <https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/elastic-ip-addresses-eip.html> |
| 7   | - Allocate Elastic IP address <br> - Gán EIP vào EC2 instance để kiểm tra <br> - Tạo SNS topic cho Auto Scaling notifications <br> - Cấu hình ASG gửi notifications đến SNS topic | 09/27/2025   | 09/27/2025      | <https://docs.aws.amazon.com/sns/latest/dg/sns-getting-started.html> |
| CN  | - Viết tài liệu giải thích các khái niệm AWS High Availability & Scaling <br> - Xem xét và tài liệu hóa kiến trúc Auto Scaling <br> - Dọn dẹp tài nguyên test nếu cần | 09/28/2025   | 09/28/2025      | <> |


### Kết quả đạt được tuần 3:

* Đã học các khái niệm và triển khai Auto Scaling:
  * Launch Templates để chuẩn hóa cấu hình instance
  * Auto Scaling Groups (ASG) để quản lý instances tự động
  * Scaling policies và triggers
  * Cấu hình Min/Max/Desired capacity
  * Health checks và thay thế instances

* Đã tạo thành công Launch Template:
  * Cấu hình Launch Template với AMI, instance type, và security groups
  * Thiết lập user data scripts cho khởi tạo instance
  * Kiểm tra Launch Template bằng cách launch instances

* Đã cấu hình Auto Scaling Group:
  * Tạo ASG với các thiết lập min/max/desired capacity phù hợp
  * Gắn Launch Template vào ASG
  * Cấu hình ASG trên nhiều Availability Zones
  * Tích hợp ASG với Application Load Balancer cho high availability

* Đã triển khai dynamic scaling:
  * Tạo CloudWatch alarms để giám sát CPU utilization
  * Cấu hình scale-out policy để thêm instances khi CPU usage > 50%
  * Cấu hình scale-in policy để xóa instances khi CPU load giảm
  * Kiểm tra thành công cả hành vi scale-out và scale-in

* Đã tích hợp với Load Balancer:
  * Kết nối ASG với ALB Target Group hiện có
  * Xác minh high availability thông qua phân phối instances tự động
  * Giám sát các hoạt động Auto Scaling và instance lifecycle

* Đã triển khai Elastic IP:
  * Học các khái niệm và use cases của Elastic IP
  * Allocate Elastic IP address
  * Gán EIP vào EC2 instance để kiểm tra

* Đã thiết lập notifications:
  * Tạo SNS topic cho Auto Scaling notifications
  * Cấu hình ASG gửi scaling event notifications đến SNS
  * Kiểm tra việc gửi notifications cho các hoạt động scaling

* Đã viết tài liệu:
  * Viết tài liệu toàn diện giải thích các khái niệm AWS High Availability & Scaling
  * Tài liệu hóa kiến trúc Auto Scaling và best practices

* Đã có kinh nghiệm thực hành với AWS Auto Scaling, high availability patterns, và tự động hóa hạ tầng.


