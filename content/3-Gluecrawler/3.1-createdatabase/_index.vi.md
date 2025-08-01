---
title: "Tạo Glue Database"
date: "2025-06-27"
weight: 1
chapter: false
pre: " <b> 3.1 </b> "
---

Trong bước này, bạn sẽ tạo một database trong AWS Glue. Cơ sở dữ liệu này đóng vai trò như một danh mục metadata, nơi lưu trữ thông tin về schema và bảng được phát hiện bởi Glue Crawler.

## Các bước thực hiện:

1. Mở **AWS Glue Console**

![GLUE CreateData](/images/5.glue/01_glue.png)

2. Truy cập **Data Catalog > Databases**
3. Nhấn **Add database**

![GLUE CreateData](/images/5.glue/02_glue.png)

4. Nhập:
   - **Tên database**: `datalake_db`
   - **Location (tùy chọn)**: để trống

![GLUE CreateData](/images/5.glue/03_glue.png)

5. Nhấn **Create database**

![GLUE CreateData](/images/5.glue/04_glue.png)

{{% notice note %}}
Bạn sẽ thấy cơ sở dữ liệu mới xuất hiện trong danh sách.
{{% /notice %}}

- Cơ sở dữ liệu này chỉ được sử dụng để lưu trữ metadata chứ không lưu trữ dữ liệu thực tế.
- Bạn có thể tái sử dụng cùng một cơ sở dữ liệu cho nhiều Glue crawler hoặc Glue job khác nhau.
