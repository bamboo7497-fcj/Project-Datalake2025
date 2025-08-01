---
title: "Tạo Glue Job"
date: "2025-06-27"
weight: 1
chapter: false
pre: " <b> 4.1 </b> "
---

Trong bước này, bạn sẽ tạo một Glue Job mới bằng AWS Glue Studio. Job này sẽ dùng để biến đổi dữ liệu thô và ghi kết quả sang thư mục khác trên S3.

---

## Mục tiêu

- Tạo job ETL theo cách trực quan
- Chỉ định nguồn dữ liệu từ Glue Catalog
- Định nghĩa đầu ra S3
- Cấu hình thông tin cơ bản cho job

---

## Hướng dẫn

1. Truy cập **AWS Glue Studio** từ giao diện AWS Console.

![GLUE CreateData](/images/5.glue/23_gluejob.png)
2. Chọn **Jobs** ở thanh điều hướng bên trái.
3. Nhấn nút màu cam **[Create job]**.
4. Chọn mẫu: **Visual with a source and target**, sau đó nhấn **[Create]**.

![GLUE CreateData](/images/5.glue/24_gluejob.png)
5. Trong giao diện tạo job:
   - Đặt tên job, ví dụ: `transform-population-job`
   - Chọn IAM role đã tạo (có quyền với Glue và S3)
   - Giữ nguyên các thiết lập mặc định cho phiên bản Glue, loại worker và bookmark (nếu không có yêu cầu khác)

![GLUE CreateData](/images/5.glue/25_gluejob.png)
![GLUE CreateData](/images/5.glue/26_gluejob.png)
