---
title : "Thiết lập IAM Role, AWS Glue"
date: 2024-01-01T10:00:00+07:00
weight : 2
chapter : false
pre : " <b> 2. </b> "
---
# Giới thiệu IAM Root User

**IAM Root User** là tài khoản **quản trị cao nhất** trong AWS, được tạo tự động khi đăng ký tài khoản AWS lần đầu.  
Tài khoản này có **quyền truy cập không giới hạn** vào tất cả dịch vụ và tài nguyên trong AWS.

## Đặc điểm chính:
- **Toàn quyền** trên tất cả dịch vụ, bao gồm cả thay đổi cài đặt thanh toán và xóa tài khoản.
- Không thể xóa hoặc giới hạn quyền của Root User.
- Chỉ có **một Root User** duy nhất cho mỗi tài khoản AWS.

## Khuyến nghị bảo mật:
1. **Kích hoạt MFA (Multi-Factor Authentication)** cho Root User.
2. **Không sử dụng Root User cho công việc hàng ngày** — thay vào đó, tạo IAM user/role với quyền cần thiết.
3. **Lưu trữ thông tin đăng nhập Root User** ở nơi an toàn, chỉ sử dụng khi thực sự cần thiết (ví dụ: thay đổi billing, khôi phục tài khoản).
4. **Ghi nhật ký (CloudTrail)** để theo dõi mọi hoạt động liên quan đến Root User.

📌 **Lưu ý:** Root User nếu bị lộ thông tin đăng nhập có thể dẫn tới **mất toàn bộ quyền kiểm soát tài khoản AWS**.
## Giới thiệu AWS Glue

**AWS Glue** là dịch vụ **extract, transform, and load (ETL)** được quản lý hoàn toàn bởi Amazon Web Services.  
Dịch vụ này giúp bạn chuẩn bị và tải dữ liệu phục vụ cho phân tích, học máy, hoặc phát triển ứng dụng mà không cần quản lý máy chủ hay hạ tầng thủ công.

### Các tính năng chính
- **Serverless**: Không cần quản lý hạ tầng, AWS Glue tự động cung cấp môi trường chạy.
- **Data Catalog**: Kho metadata tập trung, lưu trữ định nghĩa bảng, schema và thông tin job.
- **Công cụ ETL tích hợp**: Tự động sinh code Python hoặc Scala cho các job ETL.
- **Lập lịch Job**: Lên lịch chạy job ETL hoặc kích hoạt dựa trên sự kiện.
- **Tích hợp dịch vụ AWS**: Hoạt động mượt mà với Amazon S3, Redshift, RDS, Athena và nhiều dịch vụ khác.

### Kiến trúc tổng quan AWS Glue
1. **Data Catalog**  
   - Lưu trữ metadata về các tập dữ liệu.  
2. **Crawlers**  
   - Tự động quét nguồn dữ liệu và cập nhật Data Catalog.  
3. **ETL Jobs**  
   - Thực hiện biến đổi và di chuyển dữ liệu, chạy trên nền Apache Spark.  
4. **Triggers & Workflow**  
   - Tự động hóa việc thực thi job và quản lý sự phụ thuộc.

### Các trường hợp sử dụng phổ biến
- Chuẩn bị dữ liệu cho phân tích và học máy.
- Tích hợp dữ liệu từ nhiều nguồn khác nhau.
- Quản lý metadata cho nhiều dịch vụ dữ liệu AWS.
- Tự động kiểm tra và biến đổi dữ liệu trong quy trình **Data Quality Management**.
