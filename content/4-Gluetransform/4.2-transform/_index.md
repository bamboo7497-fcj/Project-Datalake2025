---
title: "Designing the Transformation Pipeline"
date: "2025-06-27"
weight: 2
chapter: false
pre: " <b> 4.2 </b> "
---

In this step, you will visually define the data transformation steps using AWS Glue Studio.

---

## Configure the data source

![GLUE CreateData](/images/5.glue/27_gluejob.png)

1. Click on the **Source** node.
2. Set **Data source** to **AWS Glue Data Catalog**.

![GLUE CreateData](/images/5.glue/27.5_gluejob.png)
3. Select the database and table discovered by the Glue Crawler (e.g., `raw_raw`).

![GLUE CreateData](/images/5.glue/28_gluejob.png)
![GLUE CreateData](/images/5.glue/29_gluejob.png)

---

## Add transformation steps

1. Click **+ Add node** > **Transform** > choose **ApplyMapping** or **SelectFields**.

![GLUE CreateData](/images/5.glue/30_gluejob_new.png)
2. You can:
   - Rename fields (e.g., `pop` → `population`)
   - Change data types (e.g., from string → int)
   - Remove unnecessary columns

![GLUE CreateData](/images/5.glue/31_gluejob_new.png)

You can chain multiple transformation steps in sequence.

---

{{% notice tip %}}
Tip
{{% /notice %}}

- Preview the schema after each step.
- Ensure column data types match the expected output schema.

After completing this, proceed to configure the target node.

---

## Configure the Target Node

After defining the transformation steps, you need to create a target node to store the result in Amazon S3.

---

1. Click the **+ Add node** button below the last transformation step (e.g., `ApplyMapping` or `Change Schema`).
2. Choose **Target** > **Amazon S3**.

![GLUE CreateData](/images/5.glue/32_gluejob_new.png)

---

## Detailed Configuration for Amazon S3 Node

After adding the target node, configure the options on the right panel:

- **Name**: Give the node a name, e.g., `S3_output_parquet`.
- **Format**: Select output format as **Parquet** (better than CSV).
- **Compression type**: Select **Snappy** to reduce file size.

![GLUE CreateData](/images/5.glue/33_gluejob_new.png)
- **S3 target location**:  
  - Choose your S3 bucket (e.g., `datalake-demo-yourname`).
  - Add a prefix if desired (e.g., `processed/`).

![GLUE CreateData](/images/5.glue/34_gluejob_new.png)
![GLUE CreateData](/images/5.glue/35_gluejob_new.png)
- **Schema**: Will automatically use schema from `ApplyMapping`.
- Click **Save** to save the job.

![GLUE CreateData](/images/5.glue/36_gluejob_new.png)

---

{{% notice tip %}}
💡 Tip: Using Parquet format with Snappy compression reduces storage cost and improves Athena query performance.
{{% /notice %}}

---

After the job completes, you can check your S3 bucket to verify the output data is saved correctly.
