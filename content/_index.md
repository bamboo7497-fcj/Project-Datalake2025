---
title : "Data Lake Architecture with S3, Lake Formation, and Glue"
date :  "2025-06-27" 
weight : 1 
chapter : false
---

# Working with Data Lake Architecture using S3, Lake Formation, and Glue

### Overview

In this tutorial, you will learn how to build a modern Data Lake architecture on AWS using core services such as Amazon S3, AWS Lake Formation, and AWS Glue. This architecture enables you to ingest, catalog, transform, and govern data securely and efficiently.

Through step-by-step practice, you will work with:
- **Amazon S3**: as the storage for both raw and processed data.
- **AWS Glue**: to detect schema using crawlers and to transform data using ETL jobs.
- **Lake Formation**: to manage access control at table and column levels.
- **Athena or QuickSight**: to analyze or visualize processed data.

The following diagram illustrates the overall architecture of the Data Lake system:

![DataLakeArchitecture](/images/datalake-arch-en.png)

---

### Lab Contents

1. [Introduction](1-introduction/)
2. [Environment Setup](2-environment-setup/)
3. [Ingest and Catalog Data with Glue Crawler](3-crawler/)
4. [Transform Data Using Glue Job](4-transform/)
5. [Secure Access Using Lake Formation](5-permissions/)
6. [Visualize Data with Athena or QuickSight](6-visualization/)
7. [Clean Up Resources](7-cleanup/)