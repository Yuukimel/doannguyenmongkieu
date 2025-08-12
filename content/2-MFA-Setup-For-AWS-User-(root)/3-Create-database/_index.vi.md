---
title : "Tạo một database mới"
date: 2024-01-01T10:00:00+07:00 
weight : 3
chapter : false
pre : " <b> 2.3 </b> "
---

## Tạo database mới trong AWS Glue


1. **Mở Glue Console**
   - Vào **AWS Console** → Tìm kiếm **"AWS Glue"** → chọn **Data Catalog** → **Databases**.
![datafile](/images/03/004.png?featherlight=false&width=90pc)
2. **Nhấn** `Create database`.

3. **Nhập thông tin**:
   - **Database name**: ví dụ `orders`
   ![datafile](/images/03/005.png?featherlight=false&width=90pc)
   - **Location** *(tùy chọn)*: Nếu muốn, bạn có thể nhập đường dẫn S3 để lưu metadata
   - **Description** *(tùy chọn)*: Mô tả mục đích database, ví dụ: *Database cho dữ liệu orders trong workshop DQ*.

4. **Nhấn** `Create database`.
