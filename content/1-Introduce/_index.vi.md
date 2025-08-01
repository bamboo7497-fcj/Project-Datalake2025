---
title: "Giới Thiệu"
date: "2025-06-27"
weight: 1
chapter: false
pre: " <b> 1. </b> "
---

# Kiến trúc Data Lake trên AWS

Trong kỷ nguyên dữ liệu hiện đại, các tổ chức cần một nền tảng linh hoạt, có khả năng mở rộng và tiết kiệm chi phí để lưu trữ và phân tích dữ liệu từ nhiều nguồn khác nhau. **Data Lake Architecture** trên nền tảng AWS cung cấp giải pháp tối ưu để hiện thực hóa điều đó.

Trong kiến trúc này:
- **Amazon S3** đóng vai trò là kho lưu trữ trung tâm cho dữ liệu thô và dữ liệu đã xử lý.
- **AWS Glue** đảm nhận nhiệm vụ thu thập siêu dữ liệu (metadata), phân tích schema và xử lý ETL (Extract, Transform, Load).
- **AWS Lake Formation** giúp kiểm soát quyền truy cập dữ liệu ở cấp độ chi tiết (database, bảng, cột).
- **Amazon Athena** và **Amazon QuickSight** cho phép truy vấn và trực quan hóa dữ liệu một cách nhanh chóng mà không cần hạ tầng máy chủ.

## Mục tiêu của tài liệu

Tài liệu này hướng dẫn người học từng bước triển khai kiến trúc Data Lake trên AWS, bao gồm:

- Thiết lập kho lưu trữ dữ liệu trên Amazon S3
- Đăng ký quyền quản trị dữ liệu với Lake Formation
- Tạo Glue Crawler để phân tích schema và catalog dữ liệu
- Tạo Glue Job để transform và nạp dữ liệu
- Phân quyền chi tiết sử dụng Lake Formation
- Thực hiện truy vấn bằng Athena và trực quan hóa với QuickSight
- Dọn dẹp tài nguyên sau khi hoàn tất

## Lợi ích khi triển khai Data Lake trên AWS

- 🔹 **Linh hoạt và mở rộng tốt**: hỗ trợ lưu trữ dữ liệu cấu trúc, bán cấu trúc, phi cấu trúc.
- 🔹 **Tiết kiệm chi phí**: chỉ trả tiền cho dung lượng và truy vấn sử dụng.
- 🔹 **Tự động hóa**: tích hợp crawler và job để nhận diện và xử lý dữ liệu.
- 🔹 **Bảo mật mạnh mẽ**: sử dụng IAM và Lake Formation để kiểm soát truy cập chi tiết.
- 🔹 **Không cần máy chủ**: tận dụng Athena để truy vấn trực tiếp từ S3 mà không cần triển khai hạ tầng.
- 🔹 **Dễ dàng tích hợp BI**: kết nối QuickSight trực tiếp đến nguồn dữ liệu trong S3 thông qua Glue Catalog và Athena.

## Sơ đồ kiến trúc tổng quan

![Kiến trúc tổng thể](/images/datalake-arch-vi.png)

> 🔍 Trong các chương tiếp theo, bạn sẽ lần lượt xây dựng từng thành phần trong kiến trúc này từ đầu đến khi hoàn chỉnh một hệ thống Data Lake toàn diện.
