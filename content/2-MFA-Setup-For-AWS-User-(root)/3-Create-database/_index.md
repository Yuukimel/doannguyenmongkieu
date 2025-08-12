---
title : "Create a New Database"
date: 2024-01-01T10:00:00+07:00 
weight : 3
chapter : false
pre : " <b> 2.3 </b> "
---

## Creating a New Database in AWS Glue

1. **Open the Glue Console**  
   - Go to **AWS Console** → Search for **"AWS Glue"** → Select **Data Catalog** → **Databases**.  
   ![datafile](/images/03/004.png?featherlight=false&width=90pc)

2. **Click** `Create database`.

3. **Enter the details**:  
   - **Database name**: for example, `orders`  
     ![datafile](/images/03/005.png?featherlight=false&width=90pc)  
   - **Location** *(optional)*: You can specify an S3 path to store the metadata.  
   - **Description** *(optional)*: Describe the database purpose, for example: *Database for order data in the DQ workshop*.

4. **Click** `Create database`.
