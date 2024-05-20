---
title: "Thêm watermark vào các hình ảnh tải lên Amazon S3 sử dụng AWS Lambda"
date: "`r Sys.Date()`"
weight: 1
chapter: false
---

# Thêm watermark vào các hình ảnh tải lên Amazon S3 sử dụng AWS Lambda

#### Overview

Việc biến đổi dữ liệu một cách linh hoạt là công việc khá phổ biến ngày nay. Với các ứng dụng và môi trường khác nhau, chúng ta cần khả năng thay đổi dữ liệu phù hợp với các ca sử dụng. Bài workshop này sẽ là một ví dụ cho việc tự động hóa việc thay đổi dữ liệu, đơn giản như việc thêm watermark vào các hình ảnh được tải lên các bucket Amazon S3 sử dụng AWS Lambda. Từ đó sẽ là nền tảng để làm những biến dổi khác trước khi lưu trữ dữ liệu lên S3. Tôi sẽ đi qua từng bước chi tiết từ tạo các tài nguyên cần thiết, test luồng hoạt động và dọn dẹp sau đó. Hãy cùng bắt đầu nào

![S3](/images/1-Introduce/s3.png?featherlight=false&width=5pc) ![Lambda](/images/1-Introduce/lambda.png?featherlight=false&width=5pc)

#### Content

1. [Giới thiệu](1-introduction/)

2. [Tạo bucket trong S3](2-creates3bucket/)

3. [Tạo IAM role cho hàm Lambda](3-createiamrole/)

4. [Tạo và đóng gói hàm Lambda](4-packaginglambda/)

5. [Kiểm tra hoạt động](5-testing/)

6. [Dọn dẹp tài nguyên](6-cleanup/)
