---
title: "Worklog Tuần 9"
date: "2025-09-09T19:53:52+07:00"
weight: 1
chapter: false
pre: " <b> 1.9. </b> "
---
{{% notice warning %}}
⚠️ **Lưu ý:** Các thông tin dưới đây chỉ nhằm mục đích tham khảo, vui lòng **không sao chép nguyên văn** cho bài báo cáo của bạn kể cả warning này.
{{% /notice %}}


### Mục tiêu tuần 9:

* Học khái niệm Infrastructure as Code (IaC) với AWS CloudFormation.
* Hiểu CloudFormation template, stack và parameters.
* Viết template CloudFormation nhỏ.
* Deploy và quản lý một stack đơn giản (VPC hoặc EC2).

### Các công việc cần triển khai trong tuần này:
| Thứ | Công việc                                                                                                                                                                                   | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu                            |
| --- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------ | --------------- | ----------------------------------------- |
| 2   | - Học khái niệm IaC và tổng quan CloudFormation: template, stack, parameters, resources                                                              | 03/11/2025   | 03/11/2025      | <https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/Welcome.html> |
| 3   | - Xem các CloudFormation template mẫu từ tài liệu AWS                                                                                                 | 04/11/2025   | 04/11/2025      | <> |
| 4   | - Viết template CloudFormation nhỏ để tạo tài nguyên cơ bản (ví dụ VPC hoặc EC2)                                                                      | 05/11/2025   | 05/11/2025      | <> |
| 5   | - Deploy stack từ template <br> - Quan sát events và quá trình tạo resource                                                                           | 06/11/2025   | 06/11/2025      | <https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/cfn-console-create-stack.html> |
| 6   | - Cập nhật template và thực hiện stack update (ví dụ đổi instance type hoặc tag)                                                                     | 07/11/2025   | 07/11/2025      | <> |


### Kết quả đạt được tuần 9:

* Học các khái niệm cơ bản về Infrastructure as Code (IaC) và vai trò của CloudFormation trong tự động hóa trên AWS.

* Tìm hiểu các thành phần chính của CloudFormation:
  * Template, Resources, Parameters, Mappings, Outputs
  * Stack và vòng đời stack (create, update, delete)

* Viết template CloudFormation nhỏ để provision tập tài nguyên đơn giản (ví dụ VPC hoặc EC2 instance).

* Deploy và quản lý stack:
  * Tạo stack từ template
  * Quan sát events và quá trình tạo resource
  * Thử cập nhật và xóa stack

* Ghi chép lại các bài học và best practices khi bắt đầu làm việc với IaC trên AWS.


