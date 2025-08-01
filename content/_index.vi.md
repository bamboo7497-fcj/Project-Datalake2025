---
title : "Kiến trúc Data Lake với S3, Lake Formation và Glue"
date :  "2025-06-27" 
weight : 1 
chapter : false
---

# Làm việc với Kiến trúc Data Lake sử dụng S3, Lake Formation và Glue

### Tổng quan

Trong bài hướng dẫn này, bạn sẽ tìm hiểu cách xây dựng kiến trúc Data Lake hiện đại trên nền tảng AWS bằng cách sử dụng các dịch vụ chính như Amazon S3, AWS Lake Formation và AWS Glue. Kiến trúc này cho phép bạn thu thập, phân loại, biến đổi và quản lý quyền truy cập dữ liệu một cách bảo mật và hiệu quả.

Thông qua các bước thực hành, bạn sẽ được tiếp cận với:
- **Amazon S3**: nơi lưu trữ dữ liệu thô và dữ liệu đã xử lý.
- **AWS Glue**: để crawler phát hiện schema và transform dữ liệu.
- **Lake Formation**: để quản lý quyền truy cập theo cấp độ bảng, cột.
- **Athena hoặc QuickSight**: để trực quan hóa hoặc phân tích dữ liệu sau khi xử lý.

Sơ đồ sau minh họa kiến trúc tổng thể của hệ thống Data Lake:

![DataLakeArchitecture](/images/datalake-arch-vi.png)

---

### Nội dung hướng dẫn

1. [Giới thiệu chung](1-gioi-thieu/)
2. [Chuẩn bị môi trường](2-chuan-bi-moi-truong/)
3. [Thu thập và tạo danh mục dữ liệu với Glue Crawler](3-crawler/)
4. [Biến đổi dữ liệu bằng Glue Job](4-bien-doi-du-lieu/)
5. [Phân quyền truy cập bằng Lake Formation](5-phan-quyen/)
6. [Truy vấn và trực quan hoá dữ liệu với Athena hoặc QuickSight](6-truc-quan-hoa/)
7. [Dọn dẹp tài nguyên](7-don-dep/)
