---
title : "Deleting Resources"
date: 2024-01-01T10:00:00+07:00 
weight : 4
chapter : false
pre : " <b> 4. </b> "
---

**Contents:**  
- [Pausing Amazon S3 Buckets](#pausing-amazon-s3-buckets)  
- [AWS Glue Crawler](#aws-glue-crawler)  
- [Glue Data Quality Rule Sets (DQDL)](#glue-data-quality-rule-sets-dqdl)  

After finishing your work, you should immediately stop any services that may incur costs, even if you have not used them much — because AWS charges based on storage time and running services.

#### Pausing Amazon S3 Buckets
1. Delete files (objects) in the S3 bucket  
- Go to the S3 service.  

- Select the bucket you want to delete.  

- Open the **Objects** tab (or Files).  

- Select the files or folders to delete (you can select all).  

- Click the **Delete** button.  
![datafile](/images/04/001.png?featherlight=false&width=90pc)

2. Delete the S3 bucket  

- After the bucket is empty:  

- In the bucket list page, find the bucket you want to delete.  

- Tick the checkbox next to the bucket.  

- Click the **Delete** button.  

- Enter the bucket name as requested to confirm.  

- Click **Confirm** to complete the bucket deletion.  
![datafile](/images/04/002.png?featherlight=false&width=90pc)

#### AWS Glue Crawler
- Go to **AWS Glue** > **Crawlers**  

- Select the crawler you created → click **Delete**

#### Glue Data Quality Rule Sets (DQDL)
- Stop running or delete if you do not need to keep them  

- Go to **AWS Glue** > **Data quality** > **Rule sets** → **Delete** if unused
