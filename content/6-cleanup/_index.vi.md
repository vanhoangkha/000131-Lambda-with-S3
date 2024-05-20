---
title: "Dọn dẹp tài nguyên "
date: "`r Sys.Date()`"
weight: 6
chapter: false
pre: " <b> 6. </b> "
---

### Dọn dẹp tài nguyên

Ta sẽ xóa các tài nguyên sau một cách lần lượt:

### Xóa hàm Lambda

- Quay trở về Lambda trong **AWS Console**.

- Chọn hàm Lambda chúng ta đã tạo.

- Mở rộng mục **Action** và chọn **Delete**.

  ![Delete Lambda](/images/6-Cleanup/lambda_1.png?featherlight=false)

- Xác nhận việc xóa.

  ![Delete Lambda](/images/6-Cleanup/lambda_2.png?featherlight=false)

### Xóa bucket S3

- Truy cập S3 trong **AWS console**.

- Chọn bucket ta đã tạo trước đó.

- Click vào **Empty**

  ![Delete bucket](/images/6-Cleanup/s3_1.png?featherlight=false)

- Xác nhận xóa hết object

  ![Delete bucket](/images/6-Cleanup/s3_2.png?featherlight=false)

- Tiếp tục trở về giao diện bucket

- Bấm **Delete**

  ![Delete bucket](/images/6-Cleanup/s3_3.png?featherlight=false)

- Xác nhận xóa bucket

  ![Delete bucket](/images/6-Cleanup/s3_4.png?featherlight=false)

### Delete the IAM Policy

- Truy cập trang IAM trong **AWS console**.

- Trong menu bên trái chọn **Policies**

- Lọc ra Policy chúng ta đã tạo và chọn **`LambdaWatermarkS3`**

- Click vào **Delele**

  ![Delete IAM policy](/images/6-Cleanup/iam_pol1.png?featherlight=false)

- Xác nhận việc xóa.

  ![Delete IAM policy](/images/6-Cleanup/iam_pol2.png?featherlight=false)

### Delete the IAM Role

- Trở về giao diện IAM trong **AWS console**.

- Trong menu bên trái chọn **Roles**

- Lọc ra Role chúng ta đã tạo và chọn **`LambdaWatermarkS3Role`**

- Click vào **Delele**

  ![Delete IAM role](/images/6-Cleanup/iam_rol1.png?featherlight=false)

- Xác nhận việc xóa,

  ![Delete IAM role](/images/6-Cleanup/iam_rol2.png?featherlight=false)

Bạn đã hoàn thành xong workshop này, cảm ơn vì đã dành thời gian!!!
