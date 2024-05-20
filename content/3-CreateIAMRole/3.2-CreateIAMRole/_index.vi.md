---
title: "Tạo IAM Role"
date: "`r Sys.Date()`"
weight: 2
chapter: false
pre: " <b> 3.2 </b> "
---

### Tạo IAM Role

1. Trở về dịch vụ IAM trong Console:

- Ở menu bên phải, tìm và chọn mục **Roles**

- Sau đó click vào **Create Role**

  ![Create Role](/images/3-CreateIAMRole/startcreaterole.png?featherlight=false)

2. Trong giao diện **Create role**:

- Với mục **Select trusted entity** chọn **AWS Service**.

- Với mục **Use Case** chọn **Lambda** từ danh sách thả xuống.

  ![Create Role](/images/3-CreateIAMRole/createrole1.png?featherlight=false)

3. Gắn **IAM Policy** vào **IAM Role**:

- Trong mục **Add Permission** lọc các policy trong danh sách như ta đã làm trước đó và chọn **`LambdaWatermarkS3`**.

- Chọn **Next**

  ![Create Role](/images/3-CreateIAMRole/createrole2.png?featherlight=false)

4. Đặt tên và tạo **IAM Role**

- Hãy đặt tên role là **`LambdaWatermarkS3Role`**

  ![Create Role](/images/3-CreateIAMRole/createrole3.png?featherlight=false)

- Chọn **Create Role**

  ![Create Role](/images/3-CreateIAMRole/createrole4.png?featherlight=false)

5. Hoàn thành việc tạo **IAM Role**

   ![Create Role](/images/3-CreateIAMRole/finishrole.png?featherlight=false)

Tuyệt, bây giờ hãy bắt đầu đến với phần tạo hàm Lambda.
