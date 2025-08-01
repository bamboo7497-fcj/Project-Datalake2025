---
title: "Kiểm tra truy vấn từ Athena"
date: "2025-06-27"
weight: 3
chapter: false
pre: " <b> 5.3 </b> "
---

Trong bước này, bạn sẽ kiểm tra hiệu lực của phân quyền trong Lake Formation bằng cách truy vấn bảng đã đăng ký từ Amazon Athena.

---

## Mục tiêu

- Xác nhận phân quyền trong Lake Formation được áp dụng đúng
- Đảm bảo các cột/bảng bị giới hạn sẽ không truy cập được

---

## Hướng dẫn

1. Mở **Amazon Athena**

![ATHENA FindData](/images/6.athena/01_athena.png)
2. Chọn đúng database (vd: `datalake_demo_db`)

![ATHENA FindData](/images/6.athena/02_athena.png)
3. Thử truy vấn sau:
   ```sql
   SELECT * FROM population_summary LIMIT 10;
   ```
![ATHENA FindData](/images/6.athena/03_athena.png)

4. Nếu bạn có đầy đủ quyền, dữ liệu sẽ được trả về.

![ATHENA FindData](/images/6.athena/04_athena.png)
5. Nếu bị giới hạn quyền (vd: chặn cột), sẽ xuất hiện lỗi như `Access Denied`.

![ATHENA FindData](/images/6.athena/05_athena.png)

Bạn có thể thử với nhiều IAM user/role khác nhau để kiểm tra logic phân quyền.
