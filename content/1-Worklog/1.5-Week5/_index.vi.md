---
title: "Worklog Tuần 5"
date: "2025-09-09T19:53:52+07:00"
weight: 1
chapter: false
pre: " <b> 1.5. </b> "
---
{{% notice warning %}}
⚠️ **Lưu ý:** Các thông tin dưới đây chỉ nhằm mục đích tham khảo, vui lòng **không sao chép nguyên văn** cho bài báo cáo của bạn kể cả warning này.
{{% /notice %}}


### Mục tiêu tuần 5:

* Làm quen với khái niệm object storage trên Amazon S3.
* Thực hành upload, tổ chức và phân quyền dữ liệu trong S3 buckets.
* Bật và kiểm tra tính năng versioning trên S3.
* Tạo và test CloudFront distribution đơn giản cho S3.

### Các công việc cần triển khai trong tuần này:
| Thứ | Công việc                                                                                                                                                                                   | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu                            |
| --- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------ | --------------- | ----------------------------------------- |
| 2   | - Tìm hiểu cơ bản về Amazon S3: bucket, object, thư mục, region, mô hình pricing                                                                      | 06/10/2025   | 06/10/2025      | <https://docs.aws.amazon.com/AmazonS3/latest/userguide/Welcome.html> |
| 3   | - Tạo S3 bucket và thực hành upload/download objects <br> - Tổ chức dữ liệu theo thư mục/prefix                                                       | 07/10/2025   | 07/10/2025      | <> |
| 4   | - Cấu hình quyền truy cập S3: <br>&emsp; + So sánh bucket policy và object ACL <br>&emsp; + Test quyền private vs public                             | 08/10/2025   | 08/10/2025      | <https://docs.aws.amazon.com/AmazonS3/latest/userguide/security-best-practices.html> |
| 5   | - Bật versioning cho bucket <br> - Upload nhiều phiên bản của cùng một file và test khôi phục phiên bản cũ                                           | 09/10/2025   | 10/10/2025      | <https://docs.aws.amazon.com/AmazonS3/latest/userguide/Versioning.html> |
| 6   | - Tạo CloudFront distribution đơn giản sử dụng S3 làm origin <br> - Cấu hình behavior và thiết lập cache cơ bản                                      | 11/10/2025   | 11/10/2025      | <https://docs.aws.amazon.com/AmazonCloudFront/latest/DeveloperGuide/Introduction.html> |


### Kết quả đạt được tuần 5:

* Làm việc với Amazon S3: tạo bucket, tổ chức dữ liệu theo thư mục và upload nhiều loại file khác nhau.

* Cấu hình quyền truy cập cơ bản cho S3 và kiểm tra các mức độ truy cập (private/public, pre-signed URL nếu có).

* Bật versioning cho bucket và kiểm tra khả năng khôi phục/rollback file về các phiên bản cũ.

* Tạo CloudFront distribution sử dụng S3 bucket làm origin và:
  * Test truy cập nội dung qua domain CloudFront
  * Quan sát hành vi cache và thời gian propagate

* Ghi chép các khái niệm quan trọng về S3 và CloudFront:
  * Sự khác nhau giữa S3 và lưu trữ file truyền thống
  * Mô hình bảo mật và phân quyền cơ bản cho S3
  * Cách CloudFront giúp giảm độ trễ và giảm tải trực tiếp lên S3


