---
title: "Truy vấn và trực quan hóa với Athena & QuickSight"
date: "2025-06-27"
weight: 6
chapter: false
pre: " <b> 6. </b> "
---

Ở bước cuối này, bạn sẽ khai thác giá trị từ Data Lake bằng cách truy vấn và trực quan hóa dữ liệu. Trước tiên, dùng **Amazon Athena** để chạy truy vấn SQL với dữ liệu đã được xử lý và phân quyền. Sau đó, kết nối **Amazon QuickSight** để tạo dashboard tương tác.

---

## Phần 1 – Truy vấn dữ liệu với Athena

1. Mở **Amazon Athena**

![ATHENA FindData](/images/6.athena/01_athena.png)
2. Chọn đúng database (vd: `datalake_demo_db`)
3. Chọn bảng cần truy vấn (vd: `raw_raw`)

![ATHENA FindData](/images/6.athena/06_athena.png)
4. Chạy ví dụ:
   ```sql
   SELECT 
      region,
      COUNT(orderid) AS total_orders
   FROM raw_raw
   GROUP BY region
   ORDER BY total_orders DESC;

   ```

![ATHENA FindData](/images/6.athena/07_athena.png)
Kết quả cho thấy dữ liệu đã ETL và phân quyền đúng cách.

---

## Phần 2 – Trực quan hóa với QuickSight

1. Vào **Amazon QuickSight > Datasets**
![QUICKSIGHT FindData](/images/7.quicksight/01_quick.png)
![QUICKSIGHT FindData](/images/7.quicksight/02_quick.png)
2. Chọn **New dataset > Athena** (Tên ví dụ: `AQS_demo`)
![QUICKSIGHT FindData](/images/7.quicksight/03_quick.png)
![QUICKSIGHT FindData](/images/7.quicksight/04_quick.png)
3. Chọn database và bảng tương ứng
![QUICKSIGHT FindData](/images/7.quicksight/05_quick.png)
4. Nhập dữ liệu (Direct query hoặc SPICE)
![QUICKSIGHT FindData](/images/7.quicksight/06_quick.png)
![QUICKSIGHT FindData](/images/7.quicksight/07_quick.png)
5. Tạo biểu đồ: cột, đường, bảng tổng hợp
![QUICKSIGHT FindData](/images/7.quicksight/08_quick.png)
![QUICKSIGHT FindData](/images/7.quicksight/09_quick.png)
![QUICKSIGHT FindData](/images/7.quicksight/10_quick.png)

Giờ bạn đã có dashboard trực quan hóa dữ liệu đã xử lý từ hệ thống Data Lake!
