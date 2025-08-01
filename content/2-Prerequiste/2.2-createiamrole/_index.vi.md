---
title : "Tạo IAM Role cho Glue"
date : "2025-06-27"
weight : 2
chapter : false
pre : " <b> 2.2 </b> "
---

AWS Glue yêu cầu một IAM role có quyền cụ thể để truy cập dữ liệu trong S3, chạy crawler và job, cũng như đăng ký metadata vào Glue Data Catalog và Lake Formation.

---

## Mục tiêu:
- Tạo IAM role cho Glue
- Gán các policy cần thiết để truy cập S3, Glue, Athena và Lake Formation
- Chuẩn bị role để sử dụng cho Glue Crawler và Job

---

### 1. Mở IAM Console

- Truy cập [IAM Console](https://console.aws.amazon.com/iam/)

![IAM Createrole](/images/4.iam/01_iam.png)

- Chọn **Roles** từ menu bên trái
- Nhấn **[Create role]**

![IAM Createrole](/images/4.iam/02_iam.png)

---

### 2. Cấu hình IAM Role

- **Trusted entity**: chọn **AWS service**
- Chọn **Glue** làm trường hợp sử dụng
- Nhấn **Next**

![IAM Createrole](/images/4.iam/03_iam.png)

---

### 3. Gán các policy quyền

Tìm kiếm và gán các policy sau:

- `AWSGlueServiceRole`
- `AmazonS3FullAccess` *(hoặc chỉ định quyền chi tiết hơn nếu cần)*
- `AmazonAthenaFullAccess`
- `LakeFormationDataAdmin`

![IAM Createrole](/images/4.iam/04_iam.png)
![IAM Createrole](/images/4.iam/05_iam.png)
![IAM Createrole](/images/4.iam/06_iam.png)
![IAM Createrole](/images/4.iam/07_iam.png)

- Nhấn **Next** để tiếp tục.

---

### 4. Đặt tên cho role

- Đặt tên cho role, ví dụ: `AWSGlueDataLakeRoleSales`

![IAM Createrole](/images/4.iam/08_iam.png)

- Nhấn **Create role**

![IAM Createrole](/images/4.iam/09_iam.png)
![IAM Createrole](/images/4.iam/10_iam.png)

---

### 5. Sửa Trust Relationship

- Để cho phép cả Glue và Lake Formation assume role này, bạn cần cập nhật phần **Trust relationships** như sau:
- Vào **tab Trust relationships > Edit trust policy**, và thay toàn bộ nội dung bằng đoạn sau:


![IAM Createrole](/images/4.iam/11_iam.png)
![IAM Createrole](/images/4.iam/12_iam.png)

- Copy đoạn mã:

```json
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Effect": "Allow",
      "Principal": {
        "Service": "glue.amazonaws.com"
      },
      "Action": "sts:AssumeRole"
    },
    {
      "Effect": "Allow",
      "Principal": {
        "Service": "lakeformation.amazonaws.com"
      },
      "Action": "sts:AssumeRole"
    }
  ]
}
```
- Dán vào policy:

![IAM Createrole](/images/4.iam/13_iam.png)
![IAM Createrole](/images/4.iam/14_iam.png)

Bước này giúp đảm bảo role xuất hiện trong Lake Formation khi đăng ký vị trí S3, cũng như dùng được cho Glue Job hoặc Crawler.

---

{{% notice note %}}
Ghi chú
{{% /notice %}}

- Role này cần được chỉ định khi bạn tạo Glue Crawler hoặc Job.
- Hãy đảm bảo role có quyền truy cập đúng bucket S3 và metadata của Lake Formation.
- Bạn có thể tinh chỉnh quyền bằng cách dùng các policy tùy chỉnh thay vì `FullAccess`.

---

### Bước tiếp theo
Bạn đã sẵn sàng tạo Glue Crawler trong [Cấu hình Glue Crawler](../../3-Gluecrawler/)
