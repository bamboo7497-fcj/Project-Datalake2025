---
title : "Create IAM Role for Glue"
date : "2025-06-27"
weight : 2
chapter : false
pre : " <b> 2.2 </b> "
---

AWS Glue requires an IAM role with specific permissions to access data in S3, run crawlers and jobs, and register metadata into the Glue Data Catalog and Lake Formation.

---

## Objectives:
- Create an IAM role for Glue
- Attach required policies for S3, Glue, Athena, and Lake Formation access
- Prepare the role for use in Glue Crawlers and Jobs

---

## 1. Open the IAM console

- Go to [IAM Console](https://console.aws.amazon.com/iam/)

![IAM Createrole](/images/4.iam/01_iam.png)

- Select **Roles** from the left menu
- Click **[Create role]**

![IAM Createrole](/images/4.iam/02_iam.png)

---

## 2. Configure the IAM role

- **Trusted entity**: Select **AWS service**
- Choose **Glue** as the use case
- Click **Next**

![IAM Createrole](/images/4.iam/03_iam.png)

---

## 3. Attach permissions policies

Search and attach the following policies:

- `AWSGlueServiceRole`
- `AmazonS3FullAccess` *(or use fine-grained access if preferred)*
- `AmazonAthenaFullAccess`
- `LakeFormationDataAdmin`

![IAM Createrole](/images/4.iam/04_iam.png)
![IAM Createrole](/images/4.iam/05_iam.png)
![IAM Createrole](/images/4.iam/06_iam.png)
![IAM Createrole](/images/4.iam/07_iam.png)  

- Click **Next** to continue.

---

## 4. Name the role

- Name the role something like `AWSGlueDataLakeRoleSales`

![IAM Createrole](/images/4.iam/08_iam.png)

- Click **Create role**

![IAM Createrole](/images/4.iam/09_iam.png)
![IAM Createrole](/images/4.iam/10_iam.png)

---

## 5. Edit the Trust Relationship

- To allow both AWS Glue and Lake Formation to assume this role, update the **Trust relationships** with the following:
- Go to the **role > Trust relationships tab > Edit trust policy**, then replace the existing policy with:

![IAM Createrole](/images/4.iam/11_iam.png)
![IAM Createrole](/images/4.iam/12_iam.png)

- Copy code:

```json
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Effect": "Allow",
      "Principal": {
        "Service": "glue.amazonaws.com"
      },
      "Action": "sts:AssumeRole"
    },
    {
      "Effect": "Allow",
      "Principal": {
        "Service": "lakeformation.amazonaws.com"
      },
      "Action": "sts:AssumeRole"
    }
  ]
}
```
Paste in policy:
![IAM Createrole](/images/4.iam/13_iam.png)
![IAM Createrole](/images/4.iam/14_iam.png)

This step ensures that the role appears in Lake Formation when registering S3 locations, in addition to Glue Jobs and Crawlers.

---

{{% notice note %}}
Notes
{{% /notice %}}

- This role must be assigned when creating Glue Crawlers and Jobs.
- Make sure it has permission to access your S3 bucket and Lake Formation metadata.
- You can refine permissions further by using custom policies instead of `FullAccess` policies.

---

### Next Step
You’re ready to begin building Glue Crawlers in [Glue Crawler Setup](../../3-Gluecrawler/)
