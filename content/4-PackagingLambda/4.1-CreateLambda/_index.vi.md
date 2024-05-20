---
title: "Tạo hàm Lambda"
date: "`r Sys.Date()`"
weight: 1
chapter: false
pre: " <b> 4.1 </b> "
---

### Tạo hàm Lambda

1. Trở về giao diện **AWS Console**:

- Tìm kiếm từ khóa Lambda và Click chọn để đi đến trang chủ AWS Lambda

  ![Create Lambda Function](/images/4-PackageLambda/Create/start.png?featherlight=false)

2. Trong giao diện AWS Lambda:

- Chọn **Create a function**

  ![Create Lambda Function](/images/4-PackageLambda/Create/create1.png?featherlight=false)

3. Trong cửa sổ **Create function**:

- Chọn **Author from scratch** trong mục **Method** để tạo hàm thủ công

- Trong **Basic information**, bạn có thể đặt tên hàm Lambda là **`WatermarkS3Upload`**

- Trong **Runtime**, chọn phiên bản Python 3 mà bạn muốn.

  ![Create Lambda Function](/images/4-PackageLambda/Create/create2.png?featherlight=false)

{{% notice warning %}}

Hãy chọn môi trường chạy trong mục này giống với môi trường trong máy tính của bạn để chắc chắn nó sẽ chạy trong Lambda

{{% /notice %}}

- Mở rộng mục **Change default execution role**, chọn **Use an existing role**

- Trong danh sách thả xuống, tìm IAM Role chúng ta đã tạo trong phần trước **`LambdaWatermarkS3Role`**

- Click vào **Create function** để tạo hàm.

  ![Create Lambda Function](/images/4-PackageLambda/Create/create3.png?featherlight=false)

- Tạo hàm Lambda thành công

  ![Create Lambda Function](/images/4-PackageLambda/Create/create4.png?featherlight=false)

Tiếp theo chúng ta sẽ tạo **trigger** cần thiết để kích hoạt hàm Lambda.
