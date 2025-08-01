---
title: "Create Glue Crawler"
date: "2025-06-27"
weight: 2
chapter: false
pre: " <b> 3.2 </b> "
---

In this step, you will create an AWS Glue Crawler that scans your raw data in Amazon S3 and adds the metadata (schema) to the Glue Data Catalog.

---

## Instructions

1. Open the [AWS Glue Console](https://console.aws.amazon.com/glue/)

![GLUE CreateData](/images/5.glue/01_glue.png)

2. In the left menu, choose **Crawlers**
3. Click **[Create crawler]**

![GLUE CreateData](/images/5.glue/05_glue.png)

## Basic crawler settings
- Name: `raw-csv-crawler`
- Click **[Next]**

![GLUE CreateData](/images/5.glue/06_glue.png)

## Source data
- Choose **Data stores**

![GLUE CreateData](/images/5.glue/07_glue.png)

- Select: **S3**

![GLUE CreateData](/images/5.glue/08_glue.png)
- Add your path: `s3://your-bucket-name/raw/`

![GLUE CreateData](/images/5.glue/09_glue.png)
![GLUE CreateData](/images/5.glue/10_glue.png)
![GLUE CreateData](/images/5.glue/11_glue.png)

- Click **[Next]**

![GLUE CreateData](/images/5.glue/12_glue.png)

## IAM role
- Choose: `AWSGlueDataLakeRoleSales` or your custom IAM role
- Click **[Next]**

![GLUE CreateData](/images/5.glue/13_glue.png)

## Output
- Database: `datalake_demo_db`
- Prefix (optional): `raw_`
- Click **[Next]**.

![GLUE CreateData](/images/5.glue/14_glue.png)

- Click **[Finish]**.

![GLUE CreateData](/images/5.glue/15_glue.png)

![GLUE CreateData](/images/5.glue/16_glue.png)

---
{{% notice note %}}
This crawler scans S3 files and automatically infers schema.  
It updates the Glue Data Catalog with new or changed tables.
{{% /notice %}}

