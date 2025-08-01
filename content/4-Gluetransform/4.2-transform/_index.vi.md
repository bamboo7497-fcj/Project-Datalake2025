---
title: "Thiết kế Pipeline Biến đổi"
date: "2025-06-27"
weight: 2
chapter: false
pre: " <b> 4.2 </b> "
---

Trong bước này, bạn sẽ định nghĩa trực quan các bước biến đổi dữ liệu trong AWS Glue Studio.

---

## Cấu hình nguồn dữ liệu

![GLUE CreateData](/images/5.glue/27_gluejob.png)

1. Nhấn vào node **Source**.
2. Chọn **Data source** là **AWS Glue Data Catalog**.

![GLUE CreateData](/images/5.glue/27.5_gluejob.png)
3. Chọn database và table được phát hiện bởi Glue Crawler (ví dụ: `raw_raw`).

![GLUE CreateData](/images/5.glue/28_gluejob.png)
![GLUE CreateData](/images/5.glue/29_gluejob.png)

---

## Thêm các bước biến đổi

1. Nhấn **+ Add node** > **Transform** > chọn **ApplyMapping** hoặc **SelectFields**.

![GLUE CreateData](/images/5.glue/30_gluejob_new.png)
2. Bạn có thể:
   - Đổi tên cột (vd: `pop` → `population`)
   - Chuyển đổi kiểu dữ liệu (vd: từ string → int)
   - Loại bỏ những cột không cần thiết

![GLUE CreateData](/images/5.glue/31_gluejob_new.png)

Có thể thêm nhiều bước biến đổi liên tiếp nhau.

---

{{% notice tip %}}
Mẹo nhỏ
{{% /notice %}}

- Xem trước schema sau mỗi bước.
- Đảm bảo kiểu dữ liệu của các cột phù hợp với schema đầu ra.

Sau khi hoàn tất, bạn sẽ tiếp tục đến bước cấu hình node đích (Target).

---

## Cấu hình node đích (Target)

Sau khi hoàn tất các bước biến đổi dữ liệu, bạn cần tạo node đích để lưu kết quả ra Amazon S3.

---

1. Nhấn vào nút **+ Add node** bên dưới bước biến đổi cuối cùng (ví dụ: `ApplyMapping` hoặc `Change Schema`).
2. Chọn **Target** > **Amazon S3**.

![GLUE CreateData](/images/5.glue/32_gluejob_new.png)
---

## Cấu hình chi tiết node Amazon S3

Sau khi thêm node đích, bạn cần cấu hình các thông số bên panel phải:

- **Name**: Đặt tên cho node đích, ví dụ: `S3_output_parquet`.

- **Format**: Chọn định dạng tệp đầu ra là **Parquet** (tối ưu hơn CSV).
- **Compression type**: Chọn **Snappy** để giảm kích thước tệp.

![GLUE CreateData](/images/5.glue/33_gluejob_new.png)
- **S3 target location**:  
  - Chọn S3 bucket (ví dụ: `datalake-demo-yourname`).
  - Thêm prefix nếu muốn phân chia thư mục (ví dụ: `processed/`).

![GLUE CreateData](/images/5.glue/34_gluejob_new.png)
![GLUE CreateData](/images/5.glue/35_gluejob_new.png)
- **Schema**: Hệ thống sẽ tự động dùng schema đã được ánh xạ từ bước `ApplyMapping`.
- Nhấn **Save** để lưu job.

![GLUE CreateData](/images/5.glue/36_gluejob_new.png)
---

{{% notice tip %}}
💡 Gợi ý: Sử dụng định dạng Parquet với nén Snappy giúp giảm chi phí lưu trữ và tăng hiệu suất truy vấn với Athena.
{{% /notice %}}

---

Sau khi job hoàn tất, bạn có thể truy cập S3 để xác nhận dữ liệu đầu ra đã được lưu đúng vị trí mong muốn.
