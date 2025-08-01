---
title: "Transform Data with AWS Glue Job"
date: "2025-06-27"
weight: 4
chapter: false
pre: " <b> 4. </b> "
---

# Chapter 4 – Transform Data with AWS Glue Job

In this chapter, you will use **AWS Glue Studio** to create and run an **ETL job** that:

- Reads raw data from S3
- Applies transformations like renaming columns, mapping, filtering
- Writes processed output to a different S3 folder in Parquet format
- Automatically updates output metadata in the Glue Data Catalog

This job is a key step between ingestion and analytics, helping normalize and prepare your data.

---

## 🔍 Steps in this chapter:

- **[4.1 – Create Glue Job](4.1-createjob/)**: Create a new job in Glue Studio.
- **[4.2 – Design Transformation Pipeline](4.2-transform/)**: Apply visual data transformations.
- **[4.3 – Run and Verify Job](4.3-runandcheck/)**: Execute and validate results in S3 and Catalog.

---

After completing this chapter, you will have clean, query-ready data for **Athena** or **QuickSight**.
