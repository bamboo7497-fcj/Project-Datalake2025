---
title: "Tạo Glue Crawler"
date: "2025-06-27"
weight: 2
chapter: false
pre: " <b> 3.2 </b> "
---

Trong bước này, bạn sẽ tạo một Glue Crawler để quét dữ liệu thô trong S3 và đưa metadata (schema) vào Glue Data Catalog.

---

## Hướng dẫn

1. Truy cập [AWS Glue Console](https://console.aws.amazon.com/glue/)

![GLUE CreateData](/images/5.glue/01_glue.png)

2. Menu bên trái, chọn **Crawlers**
3. Nhấn **[Create crawler]**

![GLUE CreateData](/images/5.glue/05_glue.png)

## Cấu hình crawler cơ bản
- Name: `raw-csv-crawler`
- Nhấn **[Next]**

![GLUE CreateData](/images/5.glue/06_glue.png)

## Chọn nguồn dữ liệu
- Chọn **Data stores**

![GLUE CreateData](/images/5.glue/07_glue.png)

- Loại: **S3**

![GLUE CreateData](/images/5.glue/08_glue.png)
- Đường dẫn: `s3://tên-bucket-của-bạn/raw/`

![GLUE CreateData](/images/5.glue/09_glue.png)
![GLUE CreateData](/images/5.glue/10_glue.png)
![GLUE CreateData](/images/5.glue/11_glue.png)

- Nhấn **[Next]**

![GLUE CreateData](/images/5.glue/12_glue.png)

## Chọn IAM Role
- Role: `AWSGlueDataLakeRoleSales` hoặc role bạn đã tạo
- Nhấn **[Next]**

![GLUE CreateData](/images/5.glue/13_glue.png)

## Chọn nơi lưu kết quả
- Database: `datalake_demo_db`
- Prefix (tuỳ chọn): `raw_`
- Nhấn **[Next]**

![GLUE CreateData](/images/5.glue/14_glue.png)

- **[Finish]**

![GLUE CreateData](/images/5.glue/15_glue.png)

![GLUE CreateData](/images/5.glue/16_glue.png)
---

{{% notice note %}}
Crawler sẽ quét dữ liệu S3 và phát hiện schema tự động.  
Kết quả sẽ được ghi vào Glue Data Catalog dưới dạng bảng.
{{% /notice %}}

