---
title: "Worklog Tuần 6"
date: "2025-09-09T19:53:52+07:00"
weight: 1
chapter: false
pre: " <b> 1.6. </b> "
---
{{% notice warning %}}
⚠️ **Lưu ý:** Các thông tin dưới đây chỉ nhằm mục đích tham khảo, vui lòng **không sao chép nguyên văn** cho bài báo cáo của bạn kể cả warning này.
{{% /notice %}}


### Mục tiêu tuần 6:

* Học các khái niệm IAM: Users, Groups, Roles, Policies.
* Cấu hình quyền truy cập cơ bản theo nguyên tắc least privilege.
* Bật và kiểm tra MFA để tăng cường bảo mật tài khoản.
* Tìm hiểu CloudTrail logging để audit hoạt động API.

### Các công việc cần triển khai trong tuần này:
| Thứ | Công việc                                                                                                                                                                                   | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu                            |
| --- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------ | --------------- | ----------------------------------------- |
| 2   | - Tìm hiểu tổng quan về IAM: Users, Groups, Roles, Policies <br> - Đọc best practices (root account, MFA, least privilege)                            | 13/10/2025   | 13/10/2025      | <https://docs.aws.amazon.com/IAM/latest/UserGuide/introduction.html> |
| 3   | - Tạo IAM users và groups <br> - Gắn managed policies cho từng nhiệm vụ (ví dụ: read-only, S3 access)                                                 | 14/10/2025   | 14/10/2025      | <> |
| 4   | - Viết/đọc các JSON IAM policy đơn giản <br> - Đăng nhập bằng IAM user để test các hành động được phép/bị chặn                                         | 15/10/2025   | 15/10/2025      | <https://docs.aws.amazon.com/IAM/latest/UserGuide/access_policies.html> |
| 5   | - Bật MFA cho root và/hoặc các IAM user quan trọng <br> - Kiểm tra quy trình đăng nhập với MFA và ghi chú cách xử lý khi mất thiết bị                 | 16/10/2025   | 16/10/2025      | <https://docs.aws.amazon.com/IAM/latest/UserGuide/id_credentials_mfa.html> |
| 6   | - Bật AWS CloudTrail trong account <br> - Xem và filter các events cơ bản (login, IAM, EC2, S3…)                                                      | 17/10/2025   | 17/10/2025      | <https://docs.aws.amazon.com/awscloudtrail/latest/userguide/cloudtrail-user-guide.html> |


### Kết quả đạt được tuần 6:
* Nắm vững các khái niệm IAM cơ bản:
  * IAM Users, Groups, Roles
  * Managed policy và inline policy
  * Cấu trúc JSON của policy (Effect, Action, Resource, Condition)

* Cấu hình quyền truy cập IAM:
  * Tạo user với quyền hạn giới hạn theo từng nhiệm vụ cụ thể
  * Gắn policy theo nguyên tắc least privilege
  * Đăng nhập bằng IAM user để kiểm tra các hành động được phép/bị từ chối

* Bật Multi-Factor Authentication (MFA) cho các tài khoản quan trọng (root/IAM) và:
  * Kiểm tra quy trình đăng nhập khi bật MFA
  * Ghi chú các lưu ý về backup và khôi phục khi mất thiết bị MFA

* Bật AWS CloudTrail và:
  * Xem log hoạt động tài khoản cho các hành động quan trọng (login, IAM, EC2, S3…)
  * Hiểu vai trò của CloudTrail trong audit và điều tra bảo mật


