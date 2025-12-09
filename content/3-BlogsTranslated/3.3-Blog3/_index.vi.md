---
title: "Blog 3"
date: "2025-09-09T19:53:52+07:00"
weight: 1
chapter: false
pre: " <b> 3.3. </b> "
---



# AWS Big Data Blog

## Cộng tác dữ liệu đa tài khoản với Amazon DataZone và các công cụ phân tích AWS

Tác giả: Arun Pradeep Selvaraj, Piyush Mattoo, Mani Yamaraja — 5 tháng 3, 2025  
Chủ đề: Amazon DataZone, Amazon Redshift, AWS Glue, Hướng dẫn kỹ thuật, Tư duy lãnh đạo

Chia sẻ dữ liệu là yếu tố quan trọng đối với đổi mới, tăng trưởng và cộng tác. Gartner lưu ý rằng các tổ chức thúc đẩy chia sẻ dữ liệu vượt trội hơn các đối tác về các chỉ số giá trị kinh doanh. Một cơ chế truy cập và chia sẻ đơn giản là điều cần thiết, tuy nhiên quyền đa tài khoản và việc tìm đúng dữ liệu giữa các tài khoản là những thách thức phổ biến khi xuất bản và tiêu thụ các sản phẩm dữ liệu trên AWS.

Amazon DataZone là một dịch vụ quản lý dữ liệu được quản lý hoàn toàn để lập danh mục, khám phá, chia sẻ và quản trị dữ liệu trên AWS.

---

## Tổng quan giải pháp

Giải pháp này cho phép cộng tác đa tài khoản bằng cách sử dụng liên kết domain Amazon DataZone trong khi vẫn duy trì bảo mật và quản trị. Chúng ta xuất bản các tài sản dữ liệu thông qua danh mục dữ liệu kinh doanh Amazon DataZone để các tài khoản khác có thể khám phá chúng, sau đó truy vấn các tài sản đó từ một tài khoản AWS khác bằng các công cụ như Amazon Athena và trình chỉnh sửa truy vấn Amazon Redshift.

- **Tài khoản Producer**: lưu trữ các tài sản dữ liệu và domain Amazon DataZone.  
- **Tài khoản Consumer**: cần truy cập vào dữ liệu của producer.  
- Liên kết domain sử dụng AWS Resource Access Manager (AWS RAM). Nếu cả hai tài khoản đều trong cùng một tổ chức AWS Organizations, việc liên kết là tự động; nếu không, AWS RAM gửi lời mời để consumer chấp nhận hoặc từ chối.

Các vai trò:
- **Quản trị viên dữ liệu**: sở hữu producer/consumer; tạo domain, cấu hình/chấp nhận liên kết domain.  
- **Nhà xuất bản dữ liệu**: trong producer; tạo các dự án/môi trường xuất bản, sản xuất/xuất bản tài sản, phê duyệt yêu cầu đăng ký.  
- **Người đăng ký dữ liệu**: trong consumer; tạo các dự án/môi trường đăng ký, khám phá/đăng ký tài sản, truy vấn dữ liệu để có thông tin chi tiết.

---

## Điều kiện tiên quyết

- Hai tài khoản AWS: producer và consumer.  
- Một cluster Amazon Redshift được cung cấp hoặc nhóm làm việc Redshift Serverless trong mỗi tài khoản, được cung cấp bởi quản trị viên dữ liệu.  
- Một secret trong AWS Secrets Manager lưu trữ thông tin đăng nhập người dùng chính cho mỗi cluster/nhóm làm việc Redshift. Quản trị viên dữ liệu tạo secrets; nhà xuất bản/người đăng ký lấy ARN secret khi tạo môi trường/hồ sơ.  
- Amazon DataZone sử dụng datashares Amazon Redshift để chia sẻ đa tài khoản; cả cluster producer và consumer phải được mã hóa và sử dụng các loại RA3 được hỗ trợ (ra3.16xlarge, ra3.4xlarge, ra3.xlplus) hoặc Redshift Serverless. Xem các cân nhắc về datashare cho mã hóa.

Các bước cấp cao:
1) Tạo domain Amazon DataZone trong producer.  
2) Gửi yêu cầu liên kết domain từ producer đến consumer.  
3) Chấp nhận liên kết domain trong consumer.  
4) Thêm người dùng dữ liệu vào domain.  
5) Tạo các dự án xuất bản cho AWS Glue và Amazon Redshift (producer).  
6) Tạo môi trường Glue và Redshift để xuất bản tài sản (producer).  
7) Tạo và chạy nguồn dữ liệu cho Glue/Redshift để xuất bản tài sản vào danh mục kinh doanh.  
8) Tạo các dự án đăng ký cho Glue/Redshift (consumer).  
9) Tạo hồ sơ môi trường/môi trường cho Glue/Redshift trong các dự án đăng ký.  
10) Đăng ký các bảng Glue/Redshift và tiêu thụ thông qua Athena và trình chỉnh sửa truy vấn Redshift.

---

## Tạo domain Amazon DataZone (producer)

- Đăng nhập vào console producer với tư cách quản trị viên dữ liệu.  
- Tạo domain `Demo_cross_account_domain` (Thiết lập nhanh cho phép các blueprint và hồ sơ môi trường mặc định cho data lake và data warehouse).

---

## Yêu cầu liên kết domain (producer → consumer)

- Trong console Amazon DataZone của producer, mở domain, đi tới **Associated Accounts**, nhập ID tài khoản consumer, chọn **Request association**.  
- Sử dụng policy `AWS RAM DataZonePortalReadWrite` để người dùng consumer có thể gọi các API Amazon DataZone và sử dụng cổng dữ liệu.

---

## Chấp nhận liên kết domain (consumer)

- Đăng nhập vào consumer (cùng Region), mở Amazon DataZone → **View requests** → chọn domain → **Review request** → **Accept association**.  
- Domain hiển thị **associated**.  
- Bật environment blueprints: chọn domain → Blueprints → bật **DefaultDataLake** (cung cấp vai trò Glue Manage Access) và **DefaultDataWarehouse**.

---

## Thêm người dùng dữ liệu vào domain

- Với tư cách quản trị viên dữ liệu trong producer: **User management** → **Add** → **Add IAM users**.  
- Thêm các người dùng IAM publisher từ tài khoản hiện tại; thêm các người dùng IAM subscriber từ tài khoản consumer được liên kết.

---

## Tạo các dự án xuất bản (producer)

- Nhà xuất bản dữ liệu trong producer tạo các dự án trong cổng dữ liệu:  
  - `Glue_Publish_Project` (tài sản AWS Glue)  
  - `Redshift_Publish_Project` (tài sản Amazon Redshift)

---

## Tạo môi trường xuất bản (producer)

### Glue
- Trong `demo_cross_account_domain`, mở `Glue_Publish_Project`, tạo môi trường `Glue_Publish_Environment` với DataLakeProfile mặc định.  
- Để trống producer_glue_db_name, consumer_glue_db_name, Workgroup_name.  
- Mở Athena (Analytics tools), đảm bảo `Glue_Publish_Environment` và cơ sở dữ liệu `glue_publish_environment_pub_db`.  
- Chạy CTAS để tạo bảng mẫu `mkt_sls_table` (mẫu bán hàng/tiếp thị). Xác minh bảng tồn tại.

### Redshift
- Trong `Redshift_Publish_Project`, tạo môi trường `Redshift_Publish_Environment` với hồ sơ data warehouse mặc định.  
- Cung cấp cluster/nhóm làm việc Redshift, tên cơ sở dữ liệu và ARN secret. Secrets phải bao gồm các tag:  
  - Cluster: `DataZone.rs.cluster: <cluster:db>`  
  - Serverless: `DataZone.rs.workgroup: <workgroup:db>`  
  - `AmazonDataZoneProject: <project_id>`  
  - `AmazonDataZoneDomain: <domain_id>`  
- Trong trình chỉnh sửa truy vấn Redshift, tạo bảng `rs_sls_tbl` thông qua CTAS (dữ liệu bán hàng mẫu). Xác minh bảng tồn tại.

---

## Xuất bản tài sản vào danh mục dữ liệu kinh doanh (producer)

### Nguồn dữ liệu Glue
- Trong `Glue_Publish_Project` → `Glue_Publish_Environment`, tạo nguồn dữ liệu `glue-publish-datasource`, loại **AWS Glue**, chọn môi trường, cơ sở dữ liệu `glue_publish_environment_pub_db`, lựa chọn bảng `*`.  
- Chạy theo yêu cầu; sau khi chạy, `mkt_sls_table` xuất hiện. Xem lại metadata → **Accept All** → **Publish Asset**.

### Nguồn dữ liệu Redshift
- Trong `Redshift_Publish_Project` → `Redshift_Publish_Environment`, tạo nguồn dữ liệu `rs-publish-datasource`, loại **Amazon Redshift**.  
- Cung cấp cluster/nhóm làm việc và secret; chọn cơ sở dữ liệu `dev`, schema `datazone_env_redshift_publish_environment`.  
- Chạy theo yêu cầu; sau khi chạy, `rs_sls_tbl` xuất hiện. Xem lại metadata → **Accept All** → **Publish Asset**.

---

## Tạo các dự án đăng ký (consumer)

- Trong cổng dữ liệu consumer, tạo:  
  - `Glue_Subscribe_Project` (cho tài sản AWS Glue)  
  - `Redshift_Subscribe_Project` (cho tài sản Amazon Redshift)

---

## Tạo hồ sơ môi trường và môi trường (consumer)

### Glue
- Tạo hồ sơ môi trường `glue_subscribe-env-profile`: Blueprint **Default Data Lake**; tài khoản = consumer; Dự án được ủy quyền = Tất cả; Xuất bản = Xuất bản từ bất kỳ cơ sở dữ liệu nào.  
- Tạo môi trường `glue_subscribe_environment` từ hồ sơ (tùy chọn: tên Glue DB producer/consumer, workgroup). Đợi cho đến khi hoàn tất.

### Redshift
- Trong `Redshift_Subscribe_Project`, tạo hồ sơ `redshift_subscribe-env-profile`: Blueprint **Default Data Warehouse**; Bộ tham số = Nhập của riêng tôi; chọn Cluster hoặc Serverless; cung cấp ARN secret Redshift; Dự án được ủy quyền = Tất cả; Xuất bản = Xuất bản bất kỳ schema nào.  
- Tạo môi trường `redshift_subscribe_environment` từ hồ sơ.

---

## Đăng ký các bảng AWS Glue và Amazon Redshift

### Đăng ký Glue
- Với tư cách người đăng ký dữ liệu (consumer), mở `Glue_Subscribe_Project`, chọn **Market Sales Table** (`mkt_sls_table`) → **Subscribe** với lý do.  
- Publisher phê duyệt; subscriber xác nhận trong **Subscribed Assets**.  
- Mở Amazon Athena (môi trường `glue_subscribe_environment`, DB `glue_subscribe_environment_sub_db`), xem trước `mkt_sls_table` và xác minh dữ liệu.

### Đăng ký Redshift
- Trong `Redshift_Subscribe_Project`, tìm kiếm **Sales Table** (`rs_sls_tbl`) → **Subscribe** với lý do.  
- Publisher phê duyệt; subscriber xác nhận trong **Subscribed Assets**.  
- Mở Redshift Query Editor V2 thông qua liên kết dự án, tạo kết nối với thông tin đăng nhập IAM tạm thời, chọn DB cho môi trường và chạy:  
  `SELECT * FROM "dev"."datazone_env_redshift_subscribe_environment"."rs_sls_tbl";`

---

## Dọn dẹp

- Xóa các dự án Amazon DataZone được tạo cho hướng dẫn.  
- Xóa domain Amazon DataZone nếu nó được tạo cho phòng thí nghiệm.  
- Xóa các cluster/nhóm làm việc Redshift và các secret Secrets Manager liên quan trong cả tài khoản producer và consumer.

---

## Tóm tắt

Chia sẻ dữ liệu đa tài khoản phức tạp do quyền và bảo mật. Giải pháp này cho thấy cách xuất bản và tiêu thụ dữ liệu trên các tài khoản AWS bằng Amazon DataZone với AWS Glue và Amazon Redshift, duy trì quản trị nhất quán và truy cập an toàn. Bạn có thể theo dõi truy cập/hoạt động với AWS Lake Formation và CloudTrail (nhật ký mặc định 90 ngày). Mở rộng mẫu này sang nhiều tài khoản hơn khi cần.

---

## Về các tác giả

- **Arun Pradeep Selvaraj** – Kỹ sư Giải pháp Cấp cao tại AWS; tập trung vào chuyển đổi số và hiện đại hóa đám mây.  
- **Piyush Mattoo** – Kiến trúc sư Giải pháp Cấp cao (Dịch vụ Tài chính) tại AWS; hơn 10 năm xây dựng các hệ thống phân tán, có thể mở rộng; Thạc sĩ Khoa học Máy tính (UMass); thích cắm trại/đi bộ đường dài.  
- **Mani Yamaraja** – Quản lý Giải pháp Khách hàng Cấp cao (Dịch vụ Tài chính) tại AWS; hơn 10 năm hướng dẫn hành trình đám mây của khách hàng; tập trung vào khách hàng, thiết kế công nghệ phù hợp với mục tiêu kinh doanh.
