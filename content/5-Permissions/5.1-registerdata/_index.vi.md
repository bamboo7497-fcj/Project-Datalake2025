---
title: "Đăng ký dữ liệu vào Lake Formation"
date: "2025-06-27"
weight: 1
chapter: false
pre: " <b> 5.1 </b> "
---

Trong bước này, bạn sẽ đăng ký đường dẫn S3 chứa dữ liệu thô hoặc đã xử lý vào Lake Formation để quản lý tập trung.

---

## Mục tiêu

- Đăng ký đường dẫn S3 vào hệ thống Lake Formation
- Cấp quyền cho Lake Formation truy cập dữ liệu

---

## Hướng dẫn

1. Vào **Lake Formation > Data lake locations**
2. Nhấn **[Register location]**

![Lake Createpermisstion](/images/2.lakeformation/01_lake.png)
![Lake Createpermisstion](/images/2.lakeformation/02_lake.png)
3. Nhập đường dẫn S3, hoặc làm theo ảnh:
   ```
   s3://your-datalake-bucket/processed/
   ```

![Lake Createpermisstion](/images/2.lakeformation/03_lake.png)
![Lake Createpermisstion](/images/2.lakeformation/04_lake.png)
![Lake Createpermisstion](/images/2.lakeformation/05_lake.png)
4. Chọn IAM role có quyền truy cập Glue và S3

![Lake Createpermisstion](/images/2.lakeformation/06_lake.png)
5. Nhấn **Register location**

![Lake Createpermisstion](/images/2.lakeformation/07_lake.png)

Sau khi đăng ký, đường dẫn S3 sẽ được quản lý theo chính sách phân quyền của Lake Formation.
