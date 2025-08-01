---
title: "Chạy và Kiểm Tra Glue Crawler"
date: "2025-06-27"
weight: 3
chapter: false
pre: " <b> 3.3 </b> "
---

Sau khi tạo Glue Crawler, bạn sẽ tiến hành chạy và kiểm tra kết quả trong Glue Data Catalog.

---

## Hướng dẫn

1. Truy cập **AWS Glue Console**

![GLUE CreateData](/images/5.glue/01_glue.png)

2. Menu bên trái chọn **Crawlers**

![GLUE CreateData](/images/5.glue/16.5_glue.png)

3. Chọn crawler của bạn (vd: `raw-csv-crawler`)
4. Nhấn **[Run crawler]**

![GLUE CreateData](/images/5.glue/18_glue.png)

![GLUE CreateData](/images/5.glue/19_glue.png)

Chờ trạng thái chuyển sang **Ready**.

![GLUE CreateData](/images/5.glue/20_glue.png)

---

## Kiểm tra kết quả:

1. Vào **Data Catalog > Tables**
2. Kiểm tra các bảng đã được tạo (vd: `raw_raw`)
3. Nhấn vào bảng để xem:
   - Các cột và kiểu dữ liệu
   - Vị trí dữ liệu trong S3
   - Thông tin phân vùng (nếu có)
   
![GLUE CreateData](/images/5.glue/20.5_glue.png)
![GLUE CreateData](/images/5.glue/22_glue.png)
---

{{% notice note %}}
Có thể chạy lại crawler bất kỳ lúc nào nếu dữ liệu thay đổi.  
Glue sẽ tự động cập nhật schema nếu dữ liệu có thay đổi cấu trúc.
{{% /notice %}}

