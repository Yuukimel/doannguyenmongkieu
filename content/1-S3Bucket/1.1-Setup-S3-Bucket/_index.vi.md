---
title : "S3 Bucket trong Workshop Data Quality Management"
date: 2024-01-01T10:00:00+07:00
weight : 1
chapter : false
pre : " <b> 1.1 </b> "
---
## Mục đích sử dụng
1. **Lưu trữ dữ liệu nguồn** (raw data) trước khi chạy profiling hoặc validation.
2. **Lưu trữ dữ liệu đã xử lý** (cleaned/validated data).
3. **Lưu trữ kết quả kiểm tra chất lượng dữ liệu** từ Glue Data Quality (report, metrics).
4. **Làm staging area** cho script hoặc file cấu hình.

## Lưu ý về chi phí
- S3 bucket **không tốn phí khi không lưu trữ dữ liệu** hoặc không phát sinh request nhiều.
- Nên **xóa file tạm** hoặc dữ liệu test không cần thiết.
- Có thể **giữ bucket rỗng** để tái sử dụng cho các bước tiếp theo.

## Khi dừng dịch vụ
- Có thể xóa dữ liệu trong bucket để tiết kiệm chi phí lưu trữ.
- Nếu muốn khởi động lại workshop, chỉ cần upload lại dữ liệu hoặc script cần thiết vào bucket.

