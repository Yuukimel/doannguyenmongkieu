---
title : "Cấu hình AWS Glue"
date: 2024-01-01T10:00:00+07:00
weight : 2
chapter : false
pre : " <b> 2.2 </b> "
---

## Bước 1: Tạo Glue Crawler để phát hiện Schema

1. Vào **AWS Glue Console** → **Crawlers** → **Create crawler**.
2. Đặt **tên crawler**: `orders-crawler`.  
![datafile](/images/03/003.png?featherlight=false&width=90pc)

3. **Nguồn dữ liệu**: S3 → Chọn `s3://dq-workshop-data/input/`.  
![datafile](/images/03/002.png?featherlight=false&width=90pc)

4. **IAM role**: Chọn role bạn đã tạo trước đó (ví dụ: `GlueDQWorkshopRole`).  
![datafile](/images/02/004.png?featherlight=false&width=90pc)  
![datafile](/images/02/005.png?featherlight=false&width=90pc)

5. **Database**: Tạo mới tên `dq_db` (hoặc chọn sẵn nếu đã có).

6. **Tên bảng**: `data`.
7. Chạy crawler → Kiểm tra xem bảng `data` đã xuất hiện trong **Glue Data Catalog** chưa.

---

## Bước 2: Chạy Data Profiling

1. Vào **Glue** → **Data Quality** → **Data quality rulesets**.
2. Chọn bảng **orders** vừa tạo ở trên.
3. Nhấn **Run data profiling**.
4. AWS Glue sẽ tự động sinh ra thông tin:
   - Tỷ lệ giá trị NULL của từng cột
   - Kiểu dữ liệu
   - Giá trị Min/Max
   - Số lượng giá trị duy nhất (Distinct count)
5. Xem kết quả:
   - Cột nào có giá trị NULL?
   - Cột nào sai định dạng?

---

## Bước 3: Tạo Bộ Quy Tắc Chất Lượng Dữ Liệu (DQDL)

1. Trong **Glue** → **Data Quality** → **Create ruleset**.
2. **Tên ruleset**: `orders_rules`.
3. **Dataset**: `dq_db.orders`.
4. Thêm các quy tắc mẫu:

```json
{
  "Rules": [
    "Completeness rule: order_id IS NOT NULL",
    "Uniqueness rule: order_id IS UNIQUE",
    "Validity rule: order_status IN ('completed','cancelled','pending')",
    "Completeness rule: total_amount IS NOT NULL",
    "Validity rule: order_date IS DATEFORMAT 'yyyy-MM-dd'"
  ]
}
