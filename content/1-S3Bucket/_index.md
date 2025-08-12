---
title : "Set up S3 Bucket"
date: 2024-01-01T10:00:00+07:00
weight : 1
chapter : false
pre : " <b> 1.</b> "
---

**Content:**
- [Initialize Data](#initialize-data)
- [Sample Data](#sample-data)
- [Upload File to S3](#upload-file-to-s3)

---

## Initialize Data
In this step, we will create a simulated dataset to test **Data Quality Rules** in AWS Glue.  
The dataset will contain order information (`order_id`, `customer_id`, `order_date`, `order_status`, `total_amount`) with some intentional data errors for testing purposes.

**How to create the file:**
1. Open a text editor (Notepad, VS Code, …)
2. Copy the content from the [Sample Data](#sample-data) section
3. Save the file as **`orders.csv`**
4. Make sure the file is encoded in UTF-8 and columns are separated by commas (`,`)

---

## Sample Data
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
