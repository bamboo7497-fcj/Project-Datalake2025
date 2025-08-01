---
title: "Chuẩn bị môi trường"
date: "2025-06-27"
weight: 2
chapter: false
pre: " <b> 2. </b> "
---


Để triển khai kiến trúc Data Lake trên AWS, người dùng cần cấu hình một số dịch vụ cốt lõi trước khi bắt đầu thu thập và xử lý dữ liệu. Chương này sẽ hướng dẫn bạn thiết lập môi trường cơ bản, bao gồm tạo vùng lưu trữ trên S3, phân quyền truy cập với Lake Formation và tạo vai trò IAM cho Glue.

---

## ✅ Mục tiêu:

- Tạo **S3 Bucket** để lưu trữ dữ liệu thô và dữ liệu đã xử lý
- Cấu hình **Lake Formation** để quản lý quyền truy cập dữ liệu
- Tạo **IAM Role** để AWS Glue có thể truy cập vào S3 và sử dụng Glue Data Catalog

---

## Nội dung chi tiết

- **[2.1 – Tạo S3 Bucket và Tải Dữ liệu Mẫu](2.1-creates3/)**  
  Hướng dẫn tạo bucket S3 với cấu trúc thư mục `raw/`, `processed/`, và tải lên file dữ liệu mẫu.   
- **[2.2 – Tạo IAM Role cho Glue](2.3-createiamrole/)**  
  Tạo IAM Role có quyền truy cập S3, Glue, Athena và Lake Formation để phục vụ cho crawler và job sau này.

---

> 🔔 Sau khi hoàn tất chương này, bạn đã sẵn sàng để khởi tạo Glue Crawler trong bước tiếp theo.