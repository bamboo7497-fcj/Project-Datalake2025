---
title: "Cleanup Resources"
date: "2025-06-27"
weight: 7
chapter: false
pre: " <b> 7. </b> "
---

Once the workshop is complete, it is important to clean up your AWS environment to avoid incurring unnecessary charges. This section provides a step-by-step guide to remove the resources created during the Data Lake Architecture setup.

## 7.1 Delete Amazon S3 Buckets

1. Open the **Amazon S3 Console**.
![S3 Clean](/images/3.s3/01_s3.png)
2. Select the S3 buckets created during the workshop (e.g., `datalake-demo-yourname`).
3. **Empty the bucket** before deletion.
![S3 Clean](/images/8.clean/01_clean.png)
- Input (`permanently delete`).
![S3 Clean](/images/8.clean/02_clean.png)
![S3 Clean](/images/8.clean/03_clean.png)
4. Click **Delete** to remove the buckets permanently.
![S3 Clean](/images/8.clean/04_clean.png)
- Input (`datalake-demo-yourname`).
![S3 Clean](/images/8.clean/05_clean.png)
![S3 Clean](/images/8.clean/06_clean.png)

{{% notice warning %}}
💡 Note: Make sure you no longer need the data before deletion.
{{% /notice %}}


## 7.2 Remove Glue Resources

1. Go to the **AWS Glue Console**.
![GLUE CreateData](/images/5.glue/01_glue.png)
2. Delete the following:
- **Crawlers**
![GLUE Clean](/images/8.clean/07_clean.png)
![GLUE Clean](/images/8.clean/08_clean.png)
![GLUE Clean](/images/8.clean/09_clean.png)
- **ETL Jobs**
![GLUE Clean](/images/8.clean/10_clean.png)
![GLUE Clean](/images/8.clean/11_clean.png)
![GLUE Clean](/images/8.clean/12_clean.png)
- **Databases** and **Tables** under the Data Catalog that are specific to this workshop.
![GLUE Clean](/images/8.clean/13_clean.png)
![GLUE Clean](/images/8.clean/14_clean.png)
![GLUE Clean](/images/8.clean/15_clean.png)


{{% notice warning %}}
⚠️ Only delete the resources related to this project. Be careful if your account shares Glue resources with other applications.
{{% /notice %}}

## 7.3 Clean Up Lake Formation

1. Go to **AWS Lake Formation** > **Data lake location** >.
![Lake Createpermisstion](/images/2.lakeformation/01_lake.png)
![GLUE Clean](/images/8.clean/16_clean.png)
2. Revoke all permissions granted to IAM roles and users.
3. Optionally, delete any **Lake Formation databases** created.
![GLUE Clean](/images/8.clean/17_clean.png)
![GLUE Clean](/images/8.clean/18_clean.png)


## 7.4 Delete IAM Roles and Policies

1. Open the **IAM Console**.
![IAM Createrole](/images/4.iam/01_iam.png)
2. Remove custom IAM roles created for Glue or Lake Formation (e.g., `AWSGlueDataLakeRoleSales`).
![GLUE Clean](/images/8.clean/19_clean.png)
![GLUE Clean](/images/8.clean/20_clean.png)
![GLUE Clean](/images/8.clean/21_clean.png)

{{% notice warning %}}
⚠️Note: Delete any inline policies attached to these roles.
{{% /notice %}}

## 7.5 Delete Athena Query Results
![S3 Clean](/images/3.s3/01_s3.png)
1. Navigate to the S3 path used for storing Athena results (usually in `aws-athena-query-results-<account-region>`).
![GLUE Clean](/images/8.clean/22_clean.png)
- Input (`permanently delete`).
![GLUE Clean](/images/8.clean/23_clean.png)
![GLUE Clean](/images/8.clean/24_clean.png)
2. Empty the folder to clean up storage and avoid unnecessary costs.
![GLUE Clean](/images/8.clean/25_clean.png)
![GLUE Clean](/images/8.clean/26_clean.png)
![GLUE Clean](/images/8.clean/27_clean.png)

## 7.6 Clean Up QuickSight

1. Open **Amazon QuickSight**.
![QUICKSIGHT FindData](/images/7.quicksight/01_quick.png)
2. Delete:
- Datasets
![GLUE Clean](/images/8.clean/28_clean.png)
![GLUE Clean](/images/8.clean/29_clean.png)
- Analyses
![GLUE Clean](/images/8.clean/30_clean.png)
![GLUE Clean](/images/8.clean/31_clean.png)
![GLUE Clean](/images/8.clean/32_clean.png)

{{% notice warning %}}
⚠️Note: Data such as dashboards and datasets cannot be recovered.
{{% /notice %}}

3. If no longer needed, you may **unsubscribe QuickSight** from the account settings to avoid further billing.
![GLUE Clean](/images/8.clean/33_clean.png)
![GLUE Clean](/images/8.clean/34_clean.png)
![GLUE Clean](/images/8.clean/35_clean.png)
![GLUE Clean](/images/8.clean/36_clean.png)
![GLUE Clean](/images/8.clean/37_clean.png)

---

Cleaning up resources is an important best practice in AWS. Not only does it prevent unexpected costs, but it also keeps your environment tidy and secure.
