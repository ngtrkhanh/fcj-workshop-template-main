---
title: "Worklog Tuần 2"
date: "2025-09-09T19:53:52+07:00"
weight: 1
chapter: false
pre: " <b> 1.2. </b> "
---
{{% notice warning %}}
⚠️ **Lưu ý:** Các thông tin dưới đây chỉ nhằm mục đích tham khảo, vui lòng **không sao chép nguyên văn** cho bài báo cáo của bạn kể cả warning này.
{{% /notice %}}


### Mục tiêu tuần 2:

* Học kiến trúc VPC nâng cao và các khái niệm về mạng.
* Hiểu và triển khai cấu hình public/private subnet.
* Cấu hình Internet Gateway và NAT Gateway cho kết nối mạng.
* Triển khai và quản lý EC2 instances trong VPC subnets.
* Học và triển khai Application Load Balancer (ALB) để phân phối tải.

### Các công việc cần triển khai trong tuần này:
| Thứ | Công việc                                                                                                                                                                                   | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu                            |
| --- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------ | --------------- | ----------------------------------------- |
| 2   | - Học kiến trúc VPC nâng cao: <br>&emsp; + CIDR blocks và subnetting <br>&emsp; + Public và private subnets <br>&emsp; + Route tables và routing <br>&emsp; + Internet Gateway (IGW) <br>&emsp; + NAT Gateway | 09/15/2025   | 09/15/2025      | <https://docs.aws.amazon.com/vpc/latest/userguide/what-is-amazon-vpc.html> |
| 3   | - Tạo VPC mới với CIDR block phù hợp <br> - Tạo 2 public subnets ở các Availability Zones khác nhau <br> - Tạo 2 private subnets ở các Availability Zones khác nhau <br> - Cấu hình route tables cho public và private subnets | 09/16/2025   | 09/16/2025      | <https://docs.aws.amazon.com/vpc/latest/userguide/VPC_Subnets.html> |
| 4   | - Tạo và gắn Internet Gateway vào VPC <br> - Cấu hình public route table để route traffic đến Internet Gateway <br> - Tạo NAT Gateway trong public subnet <br> - Cấu hình private route table để route traffic qua NAT Gateway | 09/17/2025   | 09/17/2025      | <https://docs.aws.amazon.com/vpc/latest/userguide/VPC_Internet_Gateway.html> <br><br> <https://docs.aws.amazon.com/vpc/latest/userguide/vpc-nat-gateway.html> |
| 5   | - Launch EC2 instance trong public subnet <br> - Cấu hình Security Groups cho HTTP/HTTPS/SSH access <br> - Kết nối SSH vào EC2 instance <br> - Kiểm tra kết nối mạng | 09/18/2025   | 09/18/2025      | <https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/EC2_GetStarted.html> |
| 6   | - Tìm hiểu về Application Load Balancer (ALB) <br> - Tạo Target Group và cấu hình health checks <br> - Tạo ALB và gắn vào Target Group <br> - Launch nhiều EC2 instances và gắn vào Target Group | 09/19/2025   | 09/19/2025      | <https://docs.aws.amazon.com/elasticloadbalancing/latest/application/introduction.html> |
| 7   | - Kiểm tra chức năng load balancing <br> - Xác minh phân phối traffic giữa các instances <br> - Kiểm tra hành vi health check | 09/20/2025   | 09/20/2025      | <> |
| CN  | - Xem xét và tài liệu hóa kiến trúc VPC <br> - Dọn dẹp tài nguyên nếu cần | 09/21/2025   | 09/21/2025      | <> |


### Kết quả đạt được tuần 2:

* Đã học các khái niệm kiến trúc VPC nâng cao:
  * CIDR blocks và thiết kế subnet
  * Cấu hình public và private subnet
  * Route tables và cơ chế routing
  * Internet Gateway cho truy cập internet công cộng
  * NAT Gateway cho truy cập internet của private subnet

* Đã tạo thành công VPC mới với:
  * 2 public subnets ở các Availability Zones khác nhau
  * 2 private subnets ở các Availability Zones khác nhau
  * Phân bổ CIDR block và thiết kế subnet phù hợp

* Đã cấu hình hạ tầng mạng:
  * Tạo và gắn Internet Gateway vào VPC
  * Cấu hình public route table để route traffic đến Internet Gateway
  * Tạo NAT Gateway trong public subnet
  * Cấu hình private route table để route traffic qua NAT Gateway

* Đã triển khai và quản lý EC2 instances:
  * Launch EC2 instance trong public subnet
  * Kết nối SSH vào EC2 instance thành công
  * Cấu hình Security Groups cho HTTP/HTTPS/SSH access
  * Kiểm tra kết nối mạng và truy cập

* Đã triển khai Application Load Balancer (ALB):
  * Học các khái niệm và use cases của ALB
  * Tạo Target Group với cấu hình health check
  * Tạo Application Load Balancer
  * Gắn nhiều EC2 instances vào Target Group
  * Kiểm tra load balancing và phân phối traffic

* Đã có kinh nghiệm thực hành với các dịch vụ mạng AWS và cấu hình EC2 nâng cao.


