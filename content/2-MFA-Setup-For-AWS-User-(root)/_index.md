---
title: "Set up IAM Role, AWS Glue"
date: 2024-01-01T10:00:00+07:00
weight: 2
chapter: false
pre: " <b> 2. </b> "
---

## Introduction to IAM Root User

The **IAM Root User** is the **highest-level administrative account** in AWS, automatically created when you first sign up for an AWS account.  
This account has **unrestricted access** to all AWS services and resources.

## Key Characteristics:
- **Full access** to all services, including the ability to modify billing settings and delete the account.
- Cannot be deleted or have its permissions restricted.
- Only **one Root User** exists for each AWS account.

## Security Recommendations:
1. **Enable Multi-Factor Authentication (MFA)** for the Root User.
2. **Avoid using the Root User for daily operations** — instead, create IAM users/roles with the necessary permissions.
3. **Store Root User credentials** in a secure location and only use them when absolutely necessary (e.g., changing billing settings, account recovery).
4. **Enable CloudTrail logging** to monitor any activity related to the Root User.

📌 **Note:** If the Root User credentials are compromised, you could **lose complete control over your AWS account**.

## Introduction to AWS Glue

**AWS Glue** is a fully managed **extract, transform, and load (ETL)** service provided by Amazon Web Services.  
It helps you prepare and load data for analytics, machine learning, and application development without having to manually manage servers or infrastructure.

### Key Features
- **Serverless**: No infrastructure to manage. AWS Glue automatically provisions the environment.
- **Data Catalog**: Centralized metadata repository to store table definitions, schema, and job metadata.
- **Built-in ETL Engine**: Automatically generates Python or Scala code for ETL jobs.
- **Job Scheduling**: Schedule ETL jobs or trigger them based on events.
- **Integration with AWS Services**: Works seamlessly with Amazon S3, Redshift, RDS, Athena, and more.

### AWS Glue Architecture Overview
1. **Data Catalog**  
   - Stores metadata about your datasets.  
2. **Crawlers**  
   - Automatically scan data sources and update the Data Catalog.  
3. **ETL Jobs**  
   - Transform and move data using Apache Spark under the hood.  
4. **Triggers & Workflow**  
   - Automate job execution and dependencies.


### Common Use Cases
- Data preparation for analytics and machine learning.
- Data integration from multiple sources.
- Metadata management across different AWS data services.
- Automated validation and transformation in **Data Quality Management** workflows.

