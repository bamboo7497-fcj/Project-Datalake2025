---
title: "Create S3 Bucket and Upload Sample Data"
date: "2025-06-27"
weight: 1
chapter: false
pre: " <b> 2.1 </b> "
---

In this step, you will create a new Amazon S3 bucket to store both raw and processed data. This bucket will act as the primary storage layer in your Data Lake Architecture and will be used by AWS Glue and Lake Formation.

Once completed, your S3 bucket will contain a well-defined folder structure supporting both input and output datasets for the Data Lake pipeline.

---

## Objectives:
- Create an Amazon S3 bucket
- Create folders: `raw/`, `processed/`
- Upload a sample CSV file **[sales_data.csv](https://docs.google.com/spreadsheets/d/19I5a0aUAFwI2Aw7lEbjFl88UlGgi-gvAzsdmF61vqhA/edit?usp=sharing)** to the `raw/` folder

---

### 1. Create a new S3 bucket

1. Navigate to the [Amazon S3 Console](https://s3.console.aws.amazon.com/s3/).
![S3 Bucket](/images/3.s3/01_s3.png)
2. Click **[Create bucket]**.
![S3 Create](/images/3.s3/02_s3.png)
3. Choose a region (e.g., `Asia Pacific (Singapore)`).
{{% notice warning %}}
Note: If you're not sure how to set the default region, please review the instructions **[here](https://000001.awsstudygroup.com/5-explore-and-configure-the-aws-management-console/5.1-config-default-region/)**.
{{% /notice %}}
4. Enter a globally unique name, such as `datalake-demo-yourname`.
![S3 Name](/images/3.s3/03_s3.png)

5. Leave other settings as default and click **[Create bucket]**.
![S3 FinishS3](/images/3.s3/04_s3.png)
![S3 FinishS3](/images/3.s3/05_s3.png)

---

### 2. Create folder structure
1. Open the bucket you just created.
![S3 OpenS3](/images/3.s3/06_s3.png)
2. Click **[Create folder]** and create the following folders:
![S3 Creatrraw](/images/3.s3/07_s3.png)
- Create folder `raw/`
![S3 Creatrraw](/images/3.s3/08_s3.png)
![S3 Creatrraw](/images/3.s3/09_s3.png)
- Create folder `processed/`
![S3 Creatrprocessed](/images/3.s3/10_s3.png)

{{% notice note %}}
These folders will help you organize data for ingestion and transformation.
{{% /notice %}}

![S3 finishfolder](/images/3.s3/11_s3.png)

---

### 3. Upload sample dataset

1. Open the `raw/` folder inside your bucket.

![S3 Upload](/images/3.s3/12_s3.png)

2. Click **[Upload]** → **[Add files]**.

![S3 Upload](/images/3.s3/13_s3.png)

3. Upload the `sales_data.csv` file that you downloaded **[above](https://docs.google.com/spreadsheets/d/19I5a0aUAFwI2Aw7lEbjFl88UlGgi-gvAzsdmF61vqhA/edit?usp=sharing)**.

![S3 Upload](/images/3.s3/14_s3.png)

4. Click **[Upload]** to finish.

![S3 FinishS3](/images/3.s3/15_s3.png)

---

{{% notice note %}}
Notes
{{% /notice %}}

- Record the full S3 path to your file (e.g., `s3://datalake-demo-yourname/sales_data.csv`) for later use in Glue Crawlers.
- Avoid using capital letters or spaces in bucket and folder names.
- The IAM Role created in [Step 2.2](../2.2-create-iam-role/) must have permission to access this bucket.

---

### Next Step
Continue to: [2.2 - Create IAM Role for Glue](../2.2-createiamrole/)
