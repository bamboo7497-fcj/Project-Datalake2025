---
title: "Cấu hình phân quyền trong Lake Formation"
date: "2025-06-27"
weight: 2
chapter: false
pre: " <b> 5.2 </b> "
---

Trong bước này, bạn sẽ phân quyền chi tiết cho người dùng hoặc IAM Role nhằm kiểm soát quyền truy cập vào bảng hoặc cột trong Data Lake.

---

## Mục tiêu

- Cấp quyền truy cập database và bảng trong Glue Catalog
- Cấu hình phân quyền theo bảng hoặc cột
- Gán quyền cho IAM user, role hoặc principal của Lake Formation

---

## Hướng dẫn

1. Truy cập **Lake Formation > Permissions**
2. Nhấn **[Grant]**

![Lake permisstion](/images/2.lakeformation/08_lake.png)
3. Chọn đối tượng được cấp quyền: IAM user hoặc role  
4. Chọn loại quyền: **Data catalog**

![Lake permisstion](/images/2.lakeformation/09_lake.png)
5. Lựa chọn:
   - **Database**: ví dụ `datalake_demo_db`
   - **Table**: ví dụ `raw_raw`

![Lake permisstion](/images/2.lakeformation/10_lake.png)
6. Chọn loại quyền:
   - `SELECT`, `ALTER`, `DESCRIBE`
   - Bật tùy chọn **Column-level permissions** nếu cần
7. Nhấn **Grant**

![Lake permisstion](/images/2.lakeformation/11_lake.png)
![Lake permisstion](/images/2.lakeformation/12_lake.png)

Lặp lại để cấp quyền khác nhau cho từng người dùng hoặc vai trò phù hợp.
