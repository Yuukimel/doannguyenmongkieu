---
title : "Thiết lập IAM root cho AWS Glue"
date: 2024-01-01T10:00:00+07:00
weight : 1
chapter : false
pre : " <b> 2.1 </b> "
---

## Cấp quyền cho AWS Glue

## Mục tiêu
Tạo một IAM Role dành cho Glue, cho phép:
- Truy cập vào S3 (đọc/ghi dữ liệu)
- Sử dụng Glue Crawlers, Jobs, Data Quality Ruleset
- Ghi log vào CloudWatch Logs (giúp theo dõi job chạy)
---

## Bước 1: Truy cập tạo role
1. Vào **IAM** → **Roles** → **Create Role**.
2. Ở bước **Select trusted entity**, chọn:
   - **AWS service**
   - **Use case**: Glue (nhập “Glue” vào ô tìm kiếm rồi chọn).
![datafile](/images/02/001.png?featherlight=false&width=90pc)
---

## Bước 2: Gán quyền (Attach permissions policies)
Tìm và tick chọn các policy sau:

![datafile](/images/02/003.png?featherlight=false&width=90pc)

| Policy name | Mục đích |
|-------------|----------|
| **AmazonS3FullAccess** *(hoặc AmazonS3ReadOnlyAccess + ghi đích danh bucket)* | Cho phép Glue đọc/ghi file vào S3 |
| **AWSGlueServiceRole** | Quyền cơ bản cho Glue (Crawler, Job, Catalog…) |
| **CloudWatchLogsFullAccess** *(hoặc chỉ định: logs:CreateLogGroup, logs:PutLogEvents)* | Cho phép Glue ghi log job chạy |

---

## Bước 3: Đặt tên Role và tạo
- **Role name**: `GlueDQWorkshopRole` *  

- **Mô tả**: "Role dành cho Glue Job đọc dữ liệu từ S3, ghi log và thực thi DQ rules"
Nhấn **Next**.

- **Mô tả**: Lựa chọn database đã thiết lập bên AWS Glue để tiến hành thêm Role
---
