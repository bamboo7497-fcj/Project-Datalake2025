---
title: "Query and Visualization with Athena & QuickSight"
date: "2025-06-27"
weight: 6
chapter: false
pre: " <b> 6. </b> "
---

In this final step, we will bring the data lake to life by extracting insight from it. We will first use **Amazon Athena** to query the processed and permissioned datasets. Then, we will connect **Amazon QuickSight** to the same data and build beautiful, interactive dashboards.

---

## Part 1 – Query Data with Athena

1. Navigate to **Amazon Athena**

![ATHENA FindData](/images/6.athena/01_athena.png)
2. Choose the correct database (e.g. `datalake_demo_db`)
3. Select the desired table (e.g. `raw_raw`)

![ATHENA FindData](/images/6.athena/06_athena.png)
4. Run a sample query:
   ```sql
   SELECT 
      region,
      COUNT(orderid) AS total_orders
   FROM raw_raw
   GROUP BY region
   ORDER BY total_orders DESC;
   ```

![ATHENA FindData](/images/6.athena/07_athena.png)
This confirms your ETL process and Lake Formation permissions work correctly.

---

## Part 2 – Visualize Data with QuickSight

1. Go to **Amazon QuickSight > Datasets**

![QUICKSIGHT FindData](/images/7.quicksight/01_quick.png)
![QUICKSIGHT FindData](/images/7.quicksight/02_quick.png)
2. Click **New dataset > Athena** (name e.g. `AQS_demo`)
![QUICKSIGHT FindData](/images/7.quicksight/03_quick.png)
![QUICKSIGHT FindData](/images/7.quicksight/04_quick.png)
3. Select the same database and table 

![QUICKSIGHT FindData](/images/7.quicksight/05_quick.png)
4. Import or SPICE data
![QUICKSIGHT FindData](/images/7.quicksight/06_quick.png)
![QUICKSIGHT FindData](/images/7.quicksight/07_quick.png)
5. Build visuals: bar chart, line chart, table
![QUICKSIGHT FindData](/images/7.quicksight/08_quick.png)
![QUICKSIGHT FindData](/images/7.quicksight/09_quick.png)
![QUICKSIGHT FindData](/images/7.quicksight/10_quick.png)


Now you have a full view of your governed, transformed Data Lake with query and visualization capability!
