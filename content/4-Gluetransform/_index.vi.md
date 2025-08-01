---
title: "Biến đổi dữ liệu với AWS Glue Job"
date: "2025-06-27"
weight: 4
chapter: false
pre: " <b> 4. </b> "
---

# Chương 4 – Biến đổi dữ liệu với AWS Glue Job

Trong chương này, bạn sẽ sử dụng **AWS Glue Studio** để tạo và chạy một **ETL job** có khả năng:

- Đọc dữ liệu thô từ S3
- Áp dụng các bước biến đổi như đổi tên cột, ánh xạ, lọc dòng
- Ghi dữ liệu đã xử lý vào thư mục khác trên S3 với định dạng Parquet
- Tự động cập nhật metadata đầu ra vào Glue Data Catalog

Job này sẽ đóng vai trò trung gian quan trọng giữa dữ liệu gốc và giai đoạn phân tích, giúp chuẩn hoá cấu trúc và nội dung dữ liệu.

---

## 🔍 Các bước trong chương:

- **[4.1 – Tạo Glue Job](4.1-createjob/)**: Tạo job mới trong Glue Studio.
- **[4.2 – Thiết kế Pipeline Biến đổi](4.2-transform/)**: Áp dụng các phép biến đổi dữ liệu.
- **[4.3 – Chạy và Kiểm Tra Job](4.3-runandcheck/)**: Thực thi và xác minh kết quả trong S3 và Glue Catalog.

---

Sau chương này, bạn sẽ có dữ liệu sạch sẵn sàng để truy vấn bằng **Athena** hoặc trực quan hóa bằng **QuickSight**.
