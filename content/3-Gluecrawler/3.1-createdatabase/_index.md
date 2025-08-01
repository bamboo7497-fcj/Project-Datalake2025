---
title: "Create Glue Database"
date: "2025-06-27"
weight: 1
chapter: false
pre: " <b> 3.1 </b> "
---

In this step, we will create a Glue database to store metadata for tables discovered by Glue Crawler. This database will act as the foundation for your Data Catalog in AWS Glue.

---

## Instructions

1. Go to [AWS Glue Console](https://console.aws.amazon.com/glue/)

![GLUE CreateData](/images/5.glue/01_glue.png)

2. From the left menu, choose **Data Catalog > Databases**
3. Click **[Add database]**

![GLUE CreateData](/images/5.glue/02_glue.png)

4. Set:
   - **Name**: `datalake_demo_db`
   - (Optional) Description: *Data Lake demo database*

![GLUE CreateData](/images/5.glue/03_glue.png)

5. Click **[Create]**

![GLUE CreateData](/images/5.glue/04_glue.png)

{{% notice note %}}
You should now see the new database in your list.
{{% /notice %}}

- The database is used only for metadata and does not store actual data.
- You can reuse the same database for multiple Glue crawlers or jobs.
