---
title: "Tạo IAM Policy"
date: "`r Sys.Date()`"
weight: 1
chapter: false
pre: " <b> 3.1 </b> "
---

### Tạo IAM Policy

1. Trở về trang **AWS Console** :

- Tìm kiếm từ khóa **IAM** và chọn để đi đến trang IAM

2. Trong giao diện quản lý IAM:

- Trong menu bên phải, tìm và chọn **Policies**

- Sau đó chọn **Create Policy**

  ![Create Policy](/images/3-CreateIAMRole/startcreatepolicy.png?featherlight=false)

3. Hãy làm theo các bước sau để tạo một IAM Policy, nó sẽ cho phép một số quyền truy cập CloudWatch Logs và bucket S3 ta đã tạo trước đó:

- Trong mục **Specify Permissions** chọn **JSON** để thêm các quyền bằng JSON.

  ![Create Policy](/images/3-CreateIAMRole/startjson.png?featherlight=false)

  {{% notice note %}}

  Bạn cũng có thể sử dụng **Visual Editor** để tạo policy thủ công bằng cách chọn các nút cần thiết theo hướng dẫn.

  {{% /notice %}}

- Bây giờ hãy sao chép đoạn code JSON vào một Code Editor trên máy của bạn.

  ```json
  {
    "Version": "2012-10-17",

    "Statement": [
      {
        "Effect": "Allow",

        "Action": [
          "logs:CreateLogStream",

          "logs:CreateLogGroup",

          "logs:PutLogEvents"
        ],

        "Resource": "*"
      },

      {
        "Effect": "Allow",

        "Action": "s3:*",

        "Resource": [
          "arn:aws:s3:::YOUR-BUCKET-NAME",

          "arn:aws:s3:::YOUR-BUCKET-NAME/*"
        ]
      }
    ]
  }
  ```

- Thay thế **YOUR-BUCKET-NAME** với tên bucket đã tạo và copy tên trước đó.

  ![Create Policy](/images/3-CreateIAMRole/pastejson.png?featherlight=false)

- Chọn **Next**.

- Đặt tên **`LambdaWatermarkS3`** cho policy mới

- Xem lại các quyền đã cấp trước đó rồi chọn **Create policy**

  ![Create Policy](/images/3-CreateIAMRole/finishpolicy.png?featherlight=false)

4. Hoàn thành việc tạo **IAM Policy**

- Trong danh sách policy, tìm theo tên **`LambdaWatermarkS3`** hay chọn lọc theo phân loại **Customer managed**, bạn sẽ tìm thấy policy mới đã được tạo.

  ![Create Policy](/images/3-CreateIAMRole/donepolicy.png?featherlight=false)

Bây giờ, chúng ta sẽ tiếp tục tạo một IAM Role và gán cho nó policy mới này.
