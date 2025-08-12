---
title : "Running Data Profiling on a Table"
date: 2024-01-01T11:00:00+07:00 
weight : 3
chapter : false
pre : " <b> 3. </b> "
---

### Step 1: Open the Table from Glue Data Catalog
1. Go to **AWS Console** → Search for **AWS Glue**.  
2. Select the **Tables** tab.  
3. Choose the database **workshop-db** *(or the name you assigned)*.  
4. Click on the table created by the crawler, for example: `orders_data`.  

![datafile](/images/03/006.png?featherlight=false&width=90pc)

---

### Step 2: Run Data Profiling
1. On the table details page, select the **Data quality** tab.  
2. Click **Run data profiling**. If no ruleset exists yet, proceed to create a Data Quality Ruleset.

**Create a Data Quality Ruleset**  
1. In the **Data quality** tab, click **Create data quality rule**.

![datafile](/images/03/007.png?featherlight=false&width=90pc)

2. In the **Create data quality ruleset** section, select:

- Ruleset name: dq_rules_orders  
- Table: workshop_data_pj  
- Create rules using: Glue Data Quality DSL  
- Click **Next**  
- Proceed to add rules

![datafile](/images/03/008.png?featherlight=false&width=90pc)

3. After setting up the rules (DQDL) for automated checks:  
- Click **Next** → **Create ruleset**  
- In the Data quality list, you will see dq_rules_orders  
- Click the **Run** button to execute data quality checks

---

### Step 3: Review Data Quality Ruleset Results

1. Open **AWS Glue Console**.  
2. On the left sidebar, select **Data quality**.  
3. You will see the list of created **rulesets**.

- **If not run yet:** click **Run** on the ruleset you created to perform data checks.  
- **If already run:** click on the ruleset name to view results.

After the ruleset runs, the results page displays:

- **Ruleset name** and **status**: `PASS` or `FAIL`  
- **Metrics**: number of error rows, pass/fail percentages  
- **Data source**: table name scanned from S3 by the crawler  
- **Last run time**: the most recent run timestamp  
- You can rerun the ruleset directly from the interface

![datafile](/images/03/009.png?featherlight=false&width=90pc)

---

📌 **AWS Glue performs profiling as follows:**  
- Counts the number of records.  
- Calculates the **NULL** ratio per column.  
- Infers data types *(string, int, date, etc.)*.  
- Counts unique values.  
- Determines **min/max** and **average** values *(if numeric)*.
