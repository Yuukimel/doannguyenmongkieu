---
title : "Mô tả dữ liệu mẫu"
date: 2024-01-01T10:00:00+07:00
weight : 2
chapter : false
pre : " <b> 1.2 </b> "
---

Dữ liệu mẫu được sử dụng trong Workshop **Data Quality Management với AWS Glue** bao gồm thông tin khách hàng và giao dịch, phục vụ cho mục đích kiểm thử các quy tắc chất lượng dữ liệu (Data Quality Rules).

## Định dạng
- **Định dạng tệp:** CSV
- **Mã hóa:** UTF-8
- **Dấu phân cách:** Dấu phẩy (`,`)

## Các cột chính
| Tên cột       | Kiểu dữ liệu | Mô tả |
|---------------|-------------|-------|
| `customer_id` | String      | Mã định danh duy nhất của khách hàng |
| `name`        | String      | Họ và tên khách hàng |
| `email`       | String      | Địa chỉ email |
| `phone`       | String      | Số điện thoại |
| `dob`         | Date        | Ngày sinh (định dạng `YYYY-MM-DD`) |
| `join_date`   | Date        | Ngày khách hàng tham gia hệ thống |
| `status`      | String      | Trạng thái khách hàng (`active`, `inactive`) |

## Các lỗi chất lượng dữ liệu giả lập
Dữ liệu mẫu cố tình chứa một số vấn đề để minh họa cho việc áp dụng Data Quality Rules:
- **Giá trị null** ở các cột bắt buộc (`customer_id`, `email`).
- **Sai định dạng** ở cột ngày sinh (`dob`).
- **Trùng lặp** `customer_id`.
- **Email không hợp lệ** (thiếu ký tự `@` hoặc domain).
- **Số điện thoại sai định dạng**.

## Mục đích
- Kiểm tra khả năng phát hiện lỗi dữ liệu của AWS Glue Data Quality.
- Thực hành viết và áp dụng **Data Quality Rule Set**.
- Đánh giá hiệu quả xử lý dữ liệu trước và sau khi áp dụng quy tắc.

