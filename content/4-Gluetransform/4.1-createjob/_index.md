---
title: "Create Glue Job"
date: "2025-06-27"
weight: 1
chapter: false
pre: " <b> 4.1 </b> "
---

In this step, we will create a new Glue Job using AWS Glue Studio. This job will be used to transform raw data and write the output to another S3 location.

---

## Objective

- Create an ETL job visually
- Set input source from Glue Catalog
- Define output S3 target
- Configure job basics

---

## Instructions

1. Navigate to **AWS Glue Studio** from the AWS Console.

![GLUE CreateData](/images/5.glue/23_gluejob.png)

2. Click **ETL Jobs** on the left sidebar.
3. Click the orange **[Create job]** button.
4. Choose the template: **Visual ETL**, then click **[Create]**.

![GLUE CreateData](/images/5.glue/24_gluejob.png)

5. In the new job editor:
   - Set job name, e.g., `transform-population-job`
   - Choose an existing IAM role (must have access to Glue and S3)
   - Leave default settings for Glue version, worker type, and bookmarks (unless required otherwise)

![GLUE CreateData](/images/5.glue/25_gluejob.png)
![GLUE CreateData](/images/5.glue/26_gluejob.png)
