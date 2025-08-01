---
title: "Chạy và Kiểm Tra Job"
date: "2025-06-27"
weight: 3
chapter: false
pre: " <b> 4.3 </b> "
---

Trong bước này, bạn sẽ chạy Glue Job và kiểm tra kết quả trong S3 và Glue Catalog.

---

## Chạy Job

1. Trong Glue Studio, nhấn nút **[Run]** ở góc phải trên cùng.

![GLUE CreateData](/images/5.glue/37_gluejob_new.png)
2. Chờ job hoàn tất. Có thể theo dõi trạng thái tại tab **Jobs > Runs**.

![GLUE CreateData](/images/5.glue/38_gluejob_new.png)
![GLUE CreateData](/images/5.glue/39_gluejob_new.png)
![GLUE CreateData](/images/5.glue/40_gluejob_new.png)


---

## Kiểm Tra Kết Quả

Sau khi job hoàn tất:

- Truy cập bucket S3 đích (vd: `datalake-demo-yourname/processed/`) để kiểm tra các file đã được tạo.

![GLUE CreateData](/images/5.glue/41_gluejob_new.png)
![GLUE CreateData](/images/5.glue/42_gluejob_new.png)
![GLUE CreateData](/images/5.glue/43_gluejob_new.png)

- Trong **Glue Data Catalog**, vào database chứa bảng đầu ra để xem schema.

---

## Tuỳ chọn: Kiểm Tra bằng Athena

1. Mở **Amazon Athena**

![ATHENA FindData](/images/6.athena/01_athena.png)

2. Chọn đúng database

![ATHENA FindData](/images/6.athena/02_athena.png)

3. Chạy truy vấn SQL mẫu:
```sql
SELECT * FROM "datalake_demo_db"."raw_raw" limit 10;
```
![ATHENA FindData](/images/6.athena/03_athena.png)
![ATHENA FindData](/images/6.athena/04_athena.png)

---

Việc này giúp xác nhận pipeline ETL của bạn đã hoạt động hoàn chỉnh.
