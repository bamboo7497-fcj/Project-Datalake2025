---
title: "Cross-check Query from Athena"
date: "2025-06-27"
weight: 3
chapter: false
pre: " <b> 5.3 </b> "
---

In this step, you will test the Lake Formation permissions by querying the registered table using Amazon Athena.

---

## Objective

- Validate if permissions set in Lake Formation are correctly applied
- Confirm restricted columns or tables are inaccessible

---

## Instructions

1. Open **Amazon Athena**

![ATHENA FindData](/images/6.athena/01_athena.png)
2. Select the correct database (e.g., `datalake_demo_db`)

![ATHENA FindData](/images/6.athena/02_athena.png)
3. Try the following query:
   ```sql
   SELECT * FROM population_summary LIMIT 10;
   ```

![ATHENA FindData](/images/6.athena/03_athena.png)
4. If you have full permission, data will return.

![ATHENA FindData](/images/6.athena/04_athena.png)

5. If access is restricted (e.g., column-level block), an error like `Access Denied` will appear.

![ATHENA FindData](/images/6.athena/05_athena.png)

You can test with different IAM users/roles to verify access control logic.
