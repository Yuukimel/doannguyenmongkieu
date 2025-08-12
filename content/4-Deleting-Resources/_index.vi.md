---
title : "Xóa tài nguyên"
date: 2024-01-01T10:00:00+07:00 
weight : 4
chapter : false
pre : " <b> 4. </b> "
---

**Nội dung:**
- [Tạm dừng AmazonS3 Bucket](#Tạm-dừng-AmazonS3-Bucket)
- [AWS Glue Crawler](#tạo-case-hỗ-trợ-với-aws-support)
- [Glue Data Quality Rule Sets (DQDL)](#tạo-case-hỗ-trợ-với-aws-support)

Sau khi hoàn thành, bạn nên dừng ngay các dịch vụ có khả năng gây phát sinh chi phí, kể cả khi bạn chưa dùng nhiều — vì AWS tính phí theo thời gian lưu trữ và chạy nền.

#### Tạm dừng AmazonS3 Bucket
1. Xóa các file (objects) trong bucket S3
- Vào dịch vụ S3.

- Chọn bucket bạn muốn xóa.

- Vào tab Objects (hoặc Files).

- Chọn các file hoặc folder cần xóa (có thể chọn tất cả).

- Nhấn nút Delete.
![datafile](/images/04/001.png?featherlight=false&width=90pc)

2. Xóa bucket S3

- Sau khi bucket đã trống:

- Trong trang danh sách bucket, tìm bucket muốn xóa.

- Tick chọn bucket.

- Nhấn nút Delete.

- Nhập tên bucket theo yêu cầu để xác nhận.

- Nhấn Confirm để hoàn tất xóa bucket.
![datafile](/images/04/002.png?featherlight=false&width=90pc)


#### AWS Glue Crawler
- Vào AWS Glue > Crawlers

- Chọn crawler bạn đã tạo → nhấn **Delete**

#### Glue Data Quality Rule Sets (DQDL)

- Không chạy nữa hoặc xóa nếu không cần giữ lại

- Vào **AWS Glue** > **Data quality** > **Rule sets** → **Delete** nếu không dùng
