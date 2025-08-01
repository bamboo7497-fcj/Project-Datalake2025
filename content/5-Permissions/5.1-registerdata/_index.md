---
title: "Register Data in Lake Formation"
date: "2025-06-27"
weight: 1
chapter: false
pre: " <b> 5.1 </b> "
---

In this step, you will register the S3 path that contains your raw or processed data as a Data Lake location in AWS Lake Formation.

---

## Objective

- Register your S3 path with Lake Formation
- Grant Lake Formation permissions to access the data

---

## Instructions



1. Go to **Lake Formation > Data lake locations**
2. Click **[Register location]**

![Lake Createpermisstion](/images/2.lakeformation/01_lake.png)
![Lake Createpermisstion](/images/2.lakeformation/02_lake.png)
3. In **Amazon S3 path**, input your bucket path or follow the example in the image:
   ```
   s3://your-datalake-bucket/processed/
   ```

![Lake Createpermisstion](/images/2.lakeformation/03_lake.png)
![Lake Createpermisstion](/images/2.lakeformation/04_lake.png)
![Lake Createpermisstion](/images/2.lakeformation/05_lake.png)
4. Choose an IAM role that has permission to access both Glue and S3

![Lake Createpermisstion](/images/2.lakeformation/06_lake.png)
5. Click **Register location**

![Lake Createpermisstion](/images/2.lakeformation/07_lake.png)

After registering, this S3 path will be managed under Lake Formation governance.
