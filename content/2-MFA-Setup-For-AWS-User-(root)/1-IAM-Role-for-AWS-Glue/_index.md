---
title: "Set up IAM Role for AWS Glue"
date: 2024-01-01T10:00:00+07:00
weight: 1
chapter: false
pre: " <b> 2.1 </b> "
---

## Granting Permissions for AWS Glue

## Objective
Create an IAM Role for Glue that allows:
- Access to S3 (read/write data)
- Use of Glue Crawlers, Jobs, and Data Quality Ruleset
- Write logs to CloudWatch Logs (for monitoring job execution)

---

## Step 1: Create the Role
1. Go to **IAM** → **Roles** → **Create Role**.
2. In **Select trusted entity**, choose:
   - **AWS service**
   - **Use case**: Glue (type “Glue” into the search box and select it).
![datafile](/images/02/001.png?featherlight=false&width=90pc)

---

## Step 2: Attach Permission Policies
Search and check the following policies:

![datafile](/images/02/003.png?featherlight=false&width=90pc)

| Policy name | Purpose |
|-------------|---------|
| **AmazonS3FullAccess** *(or AmazonS3ReadOnlyAccess + specific bucket write access)* | Allows Glue to read/write files to S3 |
| **AWSGlueServiceRole** | Basic permissions for Glue (Crawler, Job, Catalog…) |
| **CloudWatchLogsFullAccess** *(or specific permissions: logs:CreateLogGroup, logs:PutLogEvents)* | Allows Glue to write job execution logs |

---

## Step 3: Name and Create the Role
- **Role name**: `GlueDQWorkshopRole`  

- **Description**: "Role for Glue Job to read data from S3, write logs, and execute DQ rules"  
Click **Next**.  

- **Note**: Select the database set up in AWS Glue to proceed with adding the Role.
