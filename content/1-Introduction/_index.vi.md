---
title: "Giới thiệu"
date: "`r Sys.Date()`"
weight: 1
chapter: false
pre: " <b> 1. </b> "
---

## Tổng quan

Trong workshop này, Tôi sẽ thực hiện một tác vụ biến đổi object đơn giản trong AWS sử dụng AWS Lambda và Amazon S3. Bạn sẽ học được một số kiến thức cơ bản về một số dịch vụ trong AWS như S3, Lambda, IAM, CloudWatch. Kiến trúc tổng quan:

![Architechture](/images/1-Introduce/Architechture.png?featherlight=false)

## Sơ luợc về giải pháp

1. [Tạo bucket trong S3](2-creates3bucket/)

   Trong bước này, chúng ta sẽ tạo một bucket trong S3. Bên trong sẽ tạo hai thư mục (đúng hơn là prefix) trong S3, một cho ảnh gốc tải lên, và một cho ảnh sau xử lý (Đã thêm watermark) cho việc demo.

2. [Tạo IAM role cho hàm Lambda](3-createiamrole/)

   Bước này, chúng ta sẽ tạo một IAM role có đủ phân quyền cho hàm Lambda function có khả năng xem, tải ảnh để xử lý và tải lên S3 cũng như các quyền cần thiết để có thể viết logs trong CloudWatch Logs.

3. [Tạo và đóng gói hàm Lambda](4-packaginglambda/)

   Chúng ta sẽ tạo hàm lambda và đóng gói nó vào một tệp .zip bao gồm mã code cho hàm và một thư viện ngoài cần dùng cho việc xử lý ảnh

4. [Kiểm tra hoạt động](5-testing/)

   Sau khi tạo xong tài nguyên cần thiết, chúng ta sẽ test sự hoạt động của bài workshop.

5. [Dọn dẹp tài nguyên](6-cleanup/)

   Dọn dẹp lại tài nguyên trả về trạng thái ban đầu

Hãy bắt đầu với việc đăng nhập vào tài khoản AWS của bạn, tốt nhất là hãy sử dụng một tài khoản IAM với quyền admin. Sau đó chọn region bạn muốn, tôi sẽ chọn us-east-1 (N.Virginia) cho bài workshop này.
