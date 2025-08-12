---
title : "Thiết lập kết nối S3 Bucket"
date: 2024-01-01T10:00:00+07:00
weight : 1
chapter : false
pre : " <b> 1. </b> "
---

**Content:**
- [Khởi tạo dữ liệu](#khoi-tao-du-lieu)
- [Dữ liệu mẫu](#du-lieu-mau)
- [Tải file lên S3](#tai-file-S3)

---

## Khởi tạo dữ liệu
Trong bước này, chúng ta sẽ tạo một file dữ liệu giả lập để kiểm thử **Data Quality Rules** trong AWS Glue.  
Dataset sẽ chứa thông tin đơn hàng (`order_id`, `customer_id`, `order_date`, `order_status`, `total_amount`) với một số lỗi dữ liệu cố tình được thêm vào để phục vụ mục đích kiểm thử.

**Cách tạo file:**
1. Mở trình soạn thảo (Notepad, VS Code, …)
2. Sao chép nội dung từ phần [Dữ liệu mẫu](#dữ-liệu-mẫu)
3. Lưu file dưới tên **`orders.csv`**
4. Đảm bảo định dạng là UTF-8 và tách cột bằng dấu phẩy (`,`)

---

## Dữ liệu mẫu
```csv
order_id,customer_id,order_date,order_status,total_amount
1001,C001,2023-01-10,completed,120.50
1002,,2023-01-12,completed,89.00
1003,C003,2023/01/13,pending,99.99
1004,C004,2023-01-14,completed,75.25
1002,C002,2023-01-12,completed,89.00
1005,C005,2023-01-15,canceledd,105.00
1006,C006,2023-01-16,pending,error
1007,C007,2023-13-01,completed,110.00
1008,C008,,completed,130.00
1009,C009,2023-01-18,in_transit,95.00
1010,C010,2023-01-19,completed,
1011,C011,19-01-2023,completed,90.50
1012,C011,2023-01-20,completed,90.50
1013,,2023-01-21,cancelled,abc 
```
---
## Tải File Lên Amazon S3

### Bước 1: Truy cập AWS Console
- Mở trình duyệt và truy cập [AWS Management Console](https://aws.amazon.com/console/).
- Đăng nhập bằng tài khoản AWS của bạn.

### Bước 2: Mở Dịch Vụ S3
- Tìm kiếm **S3** trên thanh tìm kiếm dịch vụ.
- Nhấp chọn **S3**.

### Bước 3: Tạo Bucket Mới
1. Nhấn **Create bucket**.
2. **Bucket name**
   *(Ví dụ: `dq-workshop-data`)*  
3. **Region**: chọn `us-east-1` *(hoặc region mà bạn đã cấu hình AWS Glue)*.
4. Nếu muốn chia sẻ dữ liệu dễ dàng: bỏ chọn **Block all public access**.
5. Cuộn xuống và nhấn **Create bucket**.

### Bước 4: Upload File Dữ Liệu
1. Chọn bucket vừa tạo.
![datafile](/images/1/002.png?featherlight=false&width=90pc)

2. Nhấn **Upload**.
3. Chọn file dữ liệu mẫu (`data.csv`) từ máy tính.
![datafile](/images/1/001.png?featherlight=false&width=90pc)

4. Nhấn **Upload** để hoàn tất.
![datafile](/images/1/003.png?featherlight=false&width=90pc)

---
