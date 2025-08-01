---
title: "Tạo S3 Bucket và Tải Dữ liệu Mẫu"
date: "2025-06-27"
weight: 1
chapter: false
pre: " <b> 2.1 </b> "
---

Trong bước này, bạn sẽ tạo một bucket S3 mới dùng để lưu trữ dữ liệu thô và dữ liệu đã xử lý. Bucket này là thành phần trung tâm trong kiến trúc Data Lake, đóng vai trò nơi lưu trữ đầu vào và đầu ra cho các tiến trình AWS Glue và Lake Formation.

Sau khi hoàn tất, bucket của bạn sẽ có cấu trúc thư mục rõ ràng, hỗ trợ cho cả dữ liệu đầu vào và đầu ra từ các Glue Job.

---

## Mục tiêu:
- Tạo bucket S3
- Tạo các thư mục: `raw/`, `processed/`
- Tải file dữ liệu mẫu **[sales_data.csv](https://docs.google.com/spreadsheets/d/19I5a0aUAFwI2Aw7lEbjFl88UlGgi-gvAzsdmF61vqhA/edit?usp=sharing)** lên thư mục `raw/`.

---

### 1. Tạo bucket

1. Truy cập [AWS S3 Console](https://s3.console.aws.amazon.com/s3/)
![S3 Bucket](/images/3.s3/01_s3.png)
2. Nhấn **[Create bucket]**
![S3 Create](/images/3.s3/02_s3.png)
3. Chọn vùng AWS (ví dụ: `Asia Pacific (Singapore)`)
{{% notice warning %}}
Lưu ý : Nếu chưa biết cách thiết lập vùng mặc định thì hãy xem lại hướng dẫn tại **[đây](https://000001.awsstudygroup.com/vi/5-explore-and-configure-the-aws-management-console/5.1-config-default-region/)**.
{{% /notice %}}
4. Nhập tên bucket duy nhất toàn cầu, ví dụ: `datalake-demo-tenban`
![S3 Name](/images/3.s3/03_s3.png)
5. Giữ nguyên các thiết lập khác mặc định và nhấn **Create bucket**.
![S3 FinishS3](/images/3.s3/04_s3.png)
![S3 FinishS3](/images/3.s3/05_s3.png)
---

### 2. Tạo cấu trúc thư mục

1. Mở bucket vừa tạo
![S3 OpenS3](/images/3.s3/06_s3.png)
2. Nhấn **[Create folder]**
![S3 Creatrraw](/images/3.s3/07_s3.png)
3. Tạo các thư mục:

- Tạo thư mục `raw/`
![S3 Creatrraw](/images/3.s3/08_s3.png)
![S3 Creatrraw](/images/3.s3/09_s3.png)

- Tạo thư mục `processed/`
![S3 Creatrprocessed](/images/3.s3/10_s3.png)

{{% notice note %}}
Các thư mục này sẽ giúp bạn tổ chức dữ liệu để thu thập và chuyển đổi dữ liệu.
{{% /notice %}}

![S3 finishfolder](/images/3.s3/11_s3.png)
---

### 3. Tải lên dữ liệu mẫu

1. Mở thư mục `raw/`

![S3 Upload](/images/3.s3/12_s3.png)

2. Nhấn **[Upload]** → **[Add files]**

![S3 Upload](/images/3.s3/13_s3.png)

3. Tải lên file `sales_data.csv` đã tải ở phía **[trên](https://docs.google.com/spreadsheets/d/19I5a0aUAFwI2Aw7lEbjFl88UlGgi-gvAzsdmF61vqhA/edit?usp=sharing)**.

![S3 Upload](/images/3.s3/14_s3.png)

4. Nhấn **[Upload]** để hoàn tất.

![S3 FinishS3](/images/3.s3/15_s3.png)
---

{{% notice note %}}
Ghi chú
{{% /notice %}}

- Ghi lại đường dẫn đầy đủ đến file (vd: `s3://datalake-demo-tenban/raw/sales_data.csv`) để dùng trong bước Glue Crawler.
- Tránh dùng ký tự in hoa hoặc dấu cách trong tên bucket hoặc thư mục.
- IAM Role ở [Bước 2.3](../2.3-createiamrole/) phải có quyền truy cập bucket này.

---

### Tiếp theo
Chuyển sang: [2.2 – Tạo IAM Role cho Glue](../2.2-createiamrole/)