---
title : "Data Quality Management với Automated Validation trên AWS"
date : 2024-01-01T10:00:00+07:00
weight : 1 
chapter : false
---

# Data Quality Management với Automated Validation trên AWS
## Tổng quan

Trong môi trường dữ liệu lớn và đa nguồn, **đảm bảo chất lượng dữ liệu** là yếu tố then chốt cho các quyết định kinh doanh chính xác.  
Tuy nhiên, các lỗi như:
- Thiếu dữ liệu
- Sai định dạng
- Trùng lặp bản ghi

… vẫn thường xuyên xảy ra và gây ảnh hưởng nghiêm trọng đến kết quả phân tích.

Giải pháp **Data Quality Management với Automated Validation** giúp:
- **Tự động kiểm tra** chất lượng dữ liệu
- **Phát hiện và xử lý** dữ liệu lỗi
- **Giảm thiểu công sức kiểm tra thủ công**
- **Giám sát thời gian thực** bằng các dịch vụ AWS

---

### 📦 Dịch vụ AWS sử dụng

- **AWS Glue**  
  Dịch vụ ETL (Extract, Transform, Load) serverless, dùng để quét, phân loại dữ liệu, và định nghĩa **Data Quality Rules** thông qua Data Quality Definition Language (DQDL).

- **AWS Lambda**  
  Dịch vụ chạy mã không cần quản lý máy chủ, dùng để tự động kích hoạt kiểm tra dữ liệu, xử lý kết quả và gửi cảnh báo.

- **Amazon S3**  
  Dịch vụ lưu trữ đối tượng, dùng để chứa dữ liệu nguồn, kết quả kiểm tra, file cấu hình quy tắc, và báo cáo.

---


#### Main Content

1. [Tạo S3 bucket để tải file chứa dữ liệu  ](1-create-new-aws-account/)
2. [Cấp quyền cho IAM](2-MFA-Setup-For-AWS-User-(root))
3. [Thiết lập AWS Glue](3-create-admin-user-and-group/)
4. [Xóa tài nguyên](4-verify-new-account/)

