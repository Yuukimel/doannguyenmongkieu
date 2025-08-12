---
title : "S3 Bucket in Data Quality Management Workshop"
date: 2024-01-01T10:00:00+07:00
weight : 1
chapter : false
pre : " <b> 1.1 </b> "
---

## Purpose of Use
1. **Store raw data** before running profiling or validation.
2. **Store processed/validated data** after cleaning and checks.
3. **Store data quality check results** from Glue Data Quality (reports, metrics).
4. **Act as a staging area** for scripts or configuration files.

## Cost Considerations
- S3 bucket **incurs no cost when empty** or when requests are minimal.
- **Delete temporary files** or unnecessary test data to avoid charges.
- You can **keep an empty bucket** for reuse in later steps.

## When Stopping the Service
- You can delete the data inside the bucket to save storage costs.
- To restart the workshop, simply re-upload the required data or scripts into the bucket.
