---
title : "Sample Data Description"
date: 2024-01-01T10:00:00+07:00
weight : 2
chapter : false
pre : " <b> 1.2 </b> "
---

The sample dataset used in the **Data Quality Management with AWS Glue** Workshop contains customer and transaction information, designed for testing Data Quality Rules.

## Format
- **File format:** CSV  
- **Encoding:** UTF-8  
- **Delimiter:** Comma (`,`)  

## Main Columns
| Column Name   | Data Type | Description |
|---------------|-----------|-------------|
| `customer_id` | String    | Unique identifier for each customer |
| `name`        | String    | Full name of the customer |
| `email`       | String    | Email address |
| `phone`       | String    | Phone number |
| `dob`         | Date      | Date of birth (`YYYY-MM-DD` format) |
| `join_date`   | Date      | Date the customer joined the system |
| `status`      | String    | Customer status (`active`, `inactive`) |

## Simulated Data Quality Issues
The sample dataset is intentionally seeded with common issues to demonstrate Data Quality Rule applications:
- **Null values** in required fields (`customer_id`, `email`).
- **Invalid date format** in the `dob` column.
- **Duplicate** `customer_id` entries.
- **Invalid email format** (missing `@` symbol or domain).
- **Incorrect phone number format**.

## Purpose
- Verify AWS Glue Data Quality’s ability to detect data errors.
- Practice writing and applying a **Data Quality Rule Set**.
- Evaluate data quality before and after rule application.
