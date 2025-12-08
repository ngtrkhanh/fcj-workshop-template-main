---
title: "Worklog Tuần 10"
date: "2025-09-09T19:53:52+07:00"
weight: 2
chapter: false
pre: " <b> 1.10. </b> "
---
{{% notice warning %}}
⚠️ **Lưu ý:** Các thông tin dưới đây chỉ nhằm mục đích tham khảo, vui lòng **không sao chép nguyên văn** cho bài báo cáo của bạn kể cả warning này.
{{% /notice %}}


### Mục tiêu tuần 10:

* Học các khái niệm CI/CD cơ bản trên AWS.
* Hiểu cách AWS CodePipeline điều phối các bước build và deploy.
* Tạo pipeline đơn giản với CodeCommit làm nguồn.
* Kiểm tra tự động deploy khi có commit mới.

### Các công việc cần triển khai trong tuần này:
| Thứ | Công việc                                                                                                                                                                                   | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu                            |
| --- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------ | --------------- | ----------------------------------------- |
| 2   | - Tìm hiểu khái niệm CI/CD: các bước source, build, test, deploy                                                                                      | 10/11/2025   | 10/11/2025      | <https://docs.aws.amazon.com/codepipeline/latest/userguide/welcome.html> |
| 3   | - Tạo CodeCommit repository và push một ứng dụng hoặc code mẫu                                                                                        | 11/11/2025   | 11/11/2025      | <> |
| 4   | - Tạo CodePipeline đơn giản sử dụng CodeCommit làm source stage                                                                                       | 12/11/2025   | 12/11/2025      | <> |
| 5   | - Thêm bước build hoặc deploy cơ bản (ví dụ deploy artifact lên S3 hoặc EC2)                                                                          | 13/11/2025   | 13/11/2025      | <> |
| 6   | - Push commit mới và quan sát quá trình chạy, trạng thái của CodePipeline                                                                            | 14/11/2025   | 14/11/2025      | <> |


### Kết quả đạt được tuần 10:

* Tìm hiểu các khái niệm CI/CD ở mức tổng quan và cách áp dụng trên AWS.

* Khám phá các thành phần của AWS CodePipeline:
  * Source, Build, Deploy stages
  * Tích hợp với CodeCommit và các dịch vụ khác

* Tạo pipeline đơn giản:
  * Dùng CodeCommit làm source repository
  * Cấu hình bước deploy cơ bản (ví dụ deploy lên EC2 hoặc S3)

* Kiểm tra tự động deploy bằng cách push commit mới và quan sát quá trình chạy, trạng thái của CodePipeline.


