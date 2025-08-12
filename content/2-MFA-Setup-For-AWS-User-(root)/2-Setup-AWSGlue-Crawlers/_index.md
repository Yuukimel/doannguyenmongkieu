---
title : "Set up AWS Glue Crawlers"
date: 2024-01-01T10:00:00+07:00
weight : 2
chapter : false
pre : " <b> 2.2 </b> "
---

## Create Glue Crawler to Detect Schema

1. Go to **AWS Glue Console** → **Crawlers** → **Create crawler**.
2. Set **Crawler name**: `orders-crawler`.
![datafile](/images/03/003.png?featherlight=false&width=90pc)

3. **Data source**: S3 → Select `s3://dq-workshop-data/input/`.
![datafile](/images/03/002.png?featherlight=false&width=90pc)

4. **IAM role**: Select the role you created earlier (e.g., `GlueDQWorkshopRole`).
![datafile](/images/02/004.png?featherlight=false&width=90pc)
![datafile](/images/02/005.png?featherlight=false&width=90pc)

5. **Database**: Create a new one named `dq_db` (or choose an existing one).
[Create a new database](create-new-database/)
6. **Table name**: `data`.
7. Run the crawler → Verify if the `data` table appears in **Glue Data Catalog**.

--- 
