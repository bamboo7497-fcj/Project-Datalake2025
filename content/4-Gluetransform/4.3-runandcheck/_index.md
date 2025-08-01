---
title: "Run and Verify Job"
date: "2025-06-27"
weight: 3
chapter: false
pre: " <b> 4.3 </b> "
---

In this step, you will run the Glue Job and validate the output in S3 and Glue Catalog.

---

## Run Job

1. In Glue Studio, click **[Run]** in the top-right corner.

![GLUE CreateData](/images/5.glue/37_gluejob_new.png)

2. Wait until the job completes. You can monitor it under **Jobs > Runs** tab.

![GLUE CreateData](/images/5.glue/38_gluejob_new.png)
![GLUE CreateData](/images/5.glue/39_gluejob_new.png)
![GLUE CreateData](/images/5.glue/40_gluejob_new.png)

---

## Verify Results

After job finishes:

- Go to the destination S3 bucket (e.g., `datalake-demo-yourname/processed/`) and confirm the output files are generated.

![GLUE CreateData](/images/5.glue/41_gluejob_new.png)
![GLUE CreateData](/images/5.glue/42_gluejob_new.png)
![GLUE CreateData](/images/5.glue/43_gluejob_new.png)

- In **Glue Data Catalog**, navigate to the database where the output table was created and inspect schema.

---

## Optional Check with Athena

1. Open **Amazon Athena**

![ATHENA FindData](/images/6.athena/01_athena.png)
2. Select the correct database

![ATHENA FindData](/images/6.athena/02_athena.png)
3. Run a sample SQL query:
```sql
SELECT * FROM "datalake_demo_db"."raw_raw" limit 10;
```

![ATHENA FindData](/images/6.athena/03_athena.png)
![ATHENA FindData](/images/6.athena/04_athena.png)
---

This confirms your ETL pipeline is working end-to-end.
