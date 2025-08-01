---
title: "Dọn dẹp tài nguyên"
date: "2025-06-27"
weight: 7
chapter: false
pre: " <b> 7. </b> "
---

# Chương 7 – Dọn dẹp tài nguyên

Sau khi hoàn thành workshop, việc dọn dẹp môi trường AWS là rất quan trọng để tránh phát sinh chi phí không cần thiết. Phần này sẽ hướng dẫn từng bước cách xoá các dịch vụ đã tạo trong quá trình xây dựng kiến trúc Data Lake.

## 7.1 Xoá các Bucket S3

1. Mở **Amazon S3 Console**.
![S3 Clean](/images/3.s3/01_s3.png)
2. Chọn các bucket đã tạo trong workshop (ví dụ: `datalake-demo-yourname`).
3. **Làm trống bucket** trước khi xoá.
![S3 Clean](/images/8.clean/01_clean.png)
- Nhập (`permanently delete`).
![S3 Clean](/images/8.clean/02_clean.png)
![S3 Clean](/images/8.clean/03_clean.png)
4. Nhấn **Delete** để xoá vĩnh viễn bucket.
![S3 Clean](/images/8.clean/04_clean.png)
- Nhập (`datalake-demo-yourname`).
![S3 Clean](/images/8.clean/05_clean.png)
![S3 Clean](/images/8.clean/06_clean.png)

{{% notice warning %}}
💡 Lưu ý: Hãy chắc chắn rằng bạn không cần dữ liệu nữa trước khi xoá.
{{% /notice %}}


## 7.2 Xoá các tài nguyên AWS Glue

1. Vào **AWS Glue Console**.
![GLUE CreateData](/images/5.glue/01_glue.png)
2. Xoá các tài nguyên sau:
- **Crawler**
![GLUE Clean](/images/8.clean/07_clean.png)
![GLUE Clean](/images/8.clean/08_clean.png)
![GLUE Clean](/images/8.clean/09_clean.png)
- **ETL Job**
![GLUE Clean](/images/8.clean/10_clean.png)
![GLUE Clean](/images/8.clean/11_clean.png)
![GLUE Clean](/images/8.clean/12_clean.png)
- **Database** và **Table** trong Glue Data Catalog dành riêng cho workshop này.
![GLUE Clean](/images/8.clean/13_clean.png)
![GLUE Clean](/images/8.clean/14_clean.png)
![GLUE Clean](/images/8.clean/15_clean.png)

{{% notice warning %}}
⚠️ Chỉ xoá những tài nguyên liên quan đến dự án. Cẩn thận nếu bạn dùng chung tài nguyên Glue với các ứng dụng khác.
{{% /notice %}}


## 7.3 Xoá IAM Role và Policy

1. Mở **IAM Console**.
![IAM Createrole](/images/4.iam/01_iam.png)
2. Xoá các role IAM được tạo cho Glue hoặc Lake Formation (ví dụ: `AWSGlueDataLakeRoleSales`).
![GLUE Clean](/images/8.clean/19_clean.png)
![GLUE Clean](/images/8.clean/20_clean.png)
![GLUE Clean](/images/8.clean/21_clean.png)

{{% notice warning %}}
⚠️Chú ý: Xoá luôn các chính sách (policy) đính kèm nếu có.
{{% /notice %}}

## 7.4 Xoá kết quả truy vấn Athena
![S3 Clean](/images/3.s3/01_s3.png)
1. Tìm đường dẫn S3 được dùng để lưu kết quả Athena (thường là `aws-athena-query-results-<mã-vùng>`).
![GLUE Clean](/images/8.clean/22_clean.png)
- Nhập (`permanently delete`).
![GLUE Clean](/images/8.clean/23_clean.png)
![GLUE Clean](/images/8.clean/24_clean.png)
2. Dọn trống thư mục để tiết kiệm dung lượng và tránh tốn phí lưu trữ.
![GLUE Clean](/images/8.clean/25_clean.png)
![GLUE Clean](/images/8.clean/26_clean.png)
![GLUE Clean](/images/8.clean/27_clean.png)

## 7.5 Dọn dẹp QuickSight

1. Mở **Amazon QuickSight**.
![QUICKSIGHT FindData](/images/7.quicksight/01_quick.png)
2. Xoá:
- Dataset
![GLUE Clean](/images/8.clean/28_clean.png)
![GLUE Clean](/images/8.clean/29_clean.png)
- Analyses
![GLUE Clean](/images/8.clean/30_clean.png)
![GLUE Clean](/images/8.clean/31_clean.png)
![GLUE Clean](/images/8.clean/32_clean.png)

{{% notice warning %}}
⚠️Chú ý: Các dữ liệu như dashboard, datasets không thể khôi phục lại.
{{% /notice %}}
3. Nếu không sử dụng nữa, có thể **huỷ đăng ký QuickSight** trong phần cài đặt để ngừng bị tính phí.
![GLUE Clean](/images/8.clean/33_clean.png)
![GLUE Clean](/images/8.clean/34_clean.png)
![GLUE Clean](/images/8.clean/35_clean.png)
![GLUE Clean](/images/8.clean/36_clean.png)
![GLUE Clean](/images/8.clean/37_clean.png)

---

Việc dọn dẹp tài nguyên sau workshop là một bước thực hành quan trọng trong AWS. Nó giúp bạn tránh các khoản phí không mong muốn và đảm bảo môi trường luôn sạch sẽ, an toàn.
