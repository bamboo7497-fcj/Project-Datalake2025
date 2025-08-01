---
title: "Set Up Permissions in Lake Formation"
date: "2025-06-27"
weight: 2
chapter: false
pre: " <b> 5.2 </b> "
---


In this step, you will assign granular permissions to specific users or roles to control access to tables and columns in your Data Lake.

---

## Objective

- Grant access to Glue databases and tables
- Define permissions at table or column level
- Assign to users, roles, or Lake Formation principals

---

## Instructions

1. Go to **Lake Formation > Permissions**
2. Click **[Grant]**

![Lake permisstion](/images/2.lakeformation/08_lake.png)
3. Choose the principal: IAM user or role  
4. Choose **Data catalog** as the permission type

![Lake permisstion](/images/2.lakeformation/09_lake.png)
5. Select:
   - **Database**: e.g., `datalake_demo_db`
   - **Table**: e.g., `raw_raw`

![Lake permisstion](/images/2.lakeformation/10_lake.png)
6. Select permission type:
   - `SELECT`, `ALTER`, or `DESCRIBE`
   - Enable **Column-level permissions** if needed
7. Click **Grant**

![Lake permisstion](/images/2.lakeformation/11_lake.png)
![Lake permisstion](/images/2.lakeformation/12_lake.png)


Repeat to assign different levels of access for different roles or users.
