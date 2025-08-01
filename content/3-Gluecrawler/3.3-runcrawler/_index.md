---
title: "Run and Verify Glue Crawler"
date: "2025-06-27"
weight: 3
chapter: false
pre: " <b> 3.3 </b> "
---

After creating your Glue Crawler, the next step is to run it and verify that the data catalog is updated correctly.

---

## Instructions

1. Go to **AWS Glue Console**

![GLUE CreateData](/images/5.glue/01_glue.png)

2. In the left menu, select **Crawlers**

![GLUE CreateData](/images/5.glue/16.5_glue.png)

3. Choose your crawler (e.g., `raw-csv-crawler`)
4. Click **[Run crawler]**

![GLUE CreateData](/images/5.glue/18_glue.png)

![GLUE CreateData](/images/5.glue/19_glue.png)

Wait a few seconds until the status is **Ready**.

![GLUE CreateData](/images/5.glue/20_glue.png)

---

## Verify the result:

1. Go to **Data Catalog > Tables**
2. Check the tables that were created (e.g., `raw_raw`)
3. Click on a table to view:
   - Columns and data types
   - Location in S3
   - Partition information (if any)

![GLUE CreateData](/images/5.glue/20.5_glue.png)
![GLUE CreateData](/images/5.glue/22_glue.png)
---


### Notes

1. You can re-run the crawler any time to refresh schema if the data structure changes.  
2. Crawler will automatically update tables if the schema evolves.
