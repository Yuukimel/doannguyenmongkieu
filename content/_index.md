---
title : "Data Quality Management with Automated Validation on AWS"
date : 2024-01-01T10:00:00+07:00
weight : 1 
chapter : false
---

# Data Quality Management with Automated Validation on AWS
## Overview

In large-scale, multi-source data environments, **ensuring data quality** is critical for accurate business decision-making.  
However, common issues such as:
- Missing data
- Incorrect formats
- Duplicate records

… still frequently occur and can significantly impact analytical results.

The **Data Quality Management with Automated Validation** solution helps:
- **Automatically check** data quality
- **Detect and handle** faulty data
- **Reduce manual validation efforts**
- **Enable real-time monitoring** with AWS services

---

### 📦 AWS Services Used

- **AWS Glue**  
  A serverless ETL (Extract, Transform, Load) service used to scan, classify data, and define **Data Quality Rules** via the Data Quality Definition Language (DQDL).

- **AWS Lambda**  
  A serverless compute service used to automatically trigger data validation, process results, and send alerts.

- **Amazon S3**  
  An object storage service used to store source data, validation results, rule configuration files, and reports.

---

#### Main Content

1. [Create an S3 bucket to upload data files](1-create-new-aws-account/)
2. [Grant IAM permissions](2-MFA-Setup-For-AWS-User-(root))
3. [Set up AWS Glue](3-create-admin-user-and-group/)
4. [Delete resources](4-verify-new-account/)

