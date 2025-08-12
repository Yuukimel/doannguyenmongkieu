---
title : "Chạy Data Profiling trên bảng"
date: 2024-01-01T11:00:00+07:00 
weight : 3
chapter : false
pre : " <b> 3. </b> "
---

### Bước 1: Mở bảng từ Glue Data Catalog
1. Truy cập **AWS Console** → Tìm kiếm **AWS Glue**.
2. Chọn tab **Tables**.
3. Chọn database **workshop-db** *(hoặc tên bạn đã đặt)*.
4. Nhấn vào bảng đã được tạo từ crawler, ví dụ: `orders_data`.
![datafile](/images/03/006.png?featherlight=false&width=90pc)
---

### Bước 2: Chạy Data Profiling
1. Ở trang chi tiết bảng, chọn tab **Data quality**.
2. Nhấn **Run data profiling**, Nếu chưa có tiến hành tạo quy tắc kiểm tra chất lượng dữ liệu (Data Quality Ruleset) 

**Tạo quy tắc kiểm tra chất lượng dữ liệu (Data Quality Ruleset)**
1. Ở tab **Data quality** nhấn vào **Create data quality rule**
![datafile](/images/03/007.png?featherlight=false&width=90pc)

2. Trong phần **Create data quality ruleset**, chọn:

- Ruleset name: dq_rules_orders

- Table: workshop_data_pj

- Create rules using: Glue Data Quality DSL

- Nhấn **Next**

- Tiến hành thêm quy tắc (Rules)

![datafile](/images/03/008.png?featherlight=false&width=90pc)

3. Sau khi tiến hành thiết lập (DQDL) để kiểm tra tự động
- Nhấn **Next** → **Create ruleset**

- Trong danh sách Data quality, bạn sẽ thấy dq_rules_orders

- Nhấn nút **Run** để kiểm tra dữ liệu

---

### Bước 3: Kiểm tra kết quả của Data Quality Ruleset

1. Mở **AWS Glue Console**:
2. Trong thanh bên trái, chọn **Data quality**.
3. Bạn sẽ thấy danh sách các **ruleset** đã tạo.

- **Nếu chưa chạy:** chọn **Run** trên ruleset bạn đã tạo để thực hiện kiểm tra dữ liệu.
- **Nếu đã chạy:** chọn tên ruleset bạn muốn xem kết quả.

Sau khi ruleset đã chạy, trang kết quả sẽ hiển thị:

- **Tên ruleset** và **trạng thái**: `PASS` hoặc `FAIL`
- **Metrics**: số dòng lỗi, tỷ lệ phần trăm pass/fail
- **Data source**: tên bảng từ S3 đã được crawler scan
- **Last run time**: thời gian chạy gần nhất
- Có thể chạy lại ruleset trực tiếp từ giao diện

![datafile](/images/03/009.png?featherlight=false&width=90pc)

---
📌 **AWS Glue sẽ thực hiện profiling như sau:**
- Đếm số lượng bản ghi.
- Tính tỷ lệ **NULL** cho từng cột.
- Xác định kiểu dữ liệu inferred *(string, int, date...)*.
- Tính số giá trị duy nhất.
- Xác định giá trị **min/max** và **trung bình** *(nếu là số)*.

---
