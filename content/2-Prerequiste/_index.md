---
title: "Environment Preparation"
date: "2025-06-27"
weight: 2
chapter: false
pre: " <b> 2. </b> "
---



To implement a Data Lake Architecture on AWS, it is essential to configure several foundational services before ingesting and transforming data. This chapter guides you through the initial setup, including creating storage on S3, configuring Lake Formation, and creating IAM roles for Glue.

---

## ✅ Objectives:

- Create an **S3 Bucket** to store raw and processed datasets
- Configure **Lake Formation** to manage fine-grained data permissions
- Create an **IAM Role** for AWS Glue to access S3 and the Glue Data Catalog

---

## Detailed Contents
- **[2.1 – Create S3 Bucket and Upload Sample Data](2.1-creates3/)**  
Instructions for setting up an S3 bucket with folders `raw/`, `processed/`, and uploading a sample CSV file.
- **[2.2 – Create IAM Role for Glue](2.3-createiamrole/)**  
Create a Glue-compatible IAM Role with access to S3, Glue, Athena, and Lake Formation.

---

> 🔔 After completing this chapter, you will be ready to build your first Glue Crawler in the next step.