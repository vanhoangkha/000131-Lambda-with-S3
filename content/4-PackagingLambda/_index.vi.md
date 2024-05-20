---
title: "Tạo và đóng gói hàm Lambda"
date: "`r Sys.Date()`"
weight: 4
chapter: false
pre: " <b> 4. </b> "
---

### Tổng quan

Trong bước này, chúng ta sẽ bắt đầu tạo và viết code cho hàm Lambda với Python. Để thay đổi các object là ảnh, chúng ta thường sẽ dùng một thư viện chuyên dụng để xử lý ảnh, ta sẽ đóng gói hàm chung với một thư viện bên ngoài PIL, sử dụng hướng dẫn [Làm việc với tệp .zip trong hàm Python Lambda](https://docs.aws.amazon.com/lambda/latest/dg/python-package.html).

Hãy chắc chắn rằng bạn có môi trường Python và pip trong máy tính của bạn và note lại phiên bản Python. Tôi sẽ sử dụng python 3.8 trong máy tính Ubuntu.

Với các hệ điều hành khác nhau có thể có thao tác khác nhau nhưng về lý thuyết thì như nhau trong việc đóng gói. Quá trình demo tôi sẽ sử dụng các lệnh trong Ubuntu.

### Content

1. [Tạo hàm Lambda](4.1-createlambda)
2. [Tạo Trigger S3](4.2-createtrigger)
3. [Đóng gói và tải lên](4.3-packagelambda)
