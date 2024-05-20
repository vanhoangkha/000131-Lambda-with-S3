---
title: "Tao bucket S3"
date: "`r Sys.Date()`"
weight: 2
chapter: false
pre: " <b> 2. </b> "
---

### Overview

Trong phần này, chúng ta sẽ tạo một bucket cho bài workshop, chúng ta sẽ tạo hai prefix **source/** và **destination/** như là hai thư mục trong bucket.

Prefix hay thư mục **source/** sẽ dùng để lưu các ảnh gốc chưa chỉnh sửa ta tải lên, còn thư mục **destination/** sẽ lưu các ảnh được thêm watermark sau khi chạy hàm Lambda.

{{% notice info %}}

Trong các bucket S3 sẽ có cấu trúc **phẳng** thay vì phân tầng như các hệ thống file. Nhưng để tiện hơn cho việc quản lý, trong console sẽ hỗ trợ các khái niệm thư mục như là cách để nhóm các object cùng loại với nhau bằng cách dùng chung các prefix cho các object đó.

{{% /notice %}}

### Tạo bucket

1. Trong trang chủ console AWS:

- Nhập **S3** vào thanh tìm kiếm, dịch vụ S3 sẽ nằm trên đó, chọn mục này để vào trang S3.

  ![Go to S3](/images/2-CreateS3Bucket/start.png?featherlight=false)

- Trong console S3 click vào **Create Bucket**

  ![Create bucket](/images/2-CreateS3Bucket/startcreate.png?featherlight=false)

2. Trong trang tạo bucket:

- Chọn region mà bạn muốn

- Đặt tên cho cái bucket S3, hãy chắc chắn rằng nó thỏa mãn hướng dẫn đặt tên, và tên này phải là duy nhất trên toàn câud. Ở đây tôi sẽ đặt tên cho bucket là **`lambda-watermark-bucket-_sobatky_`**

  ![Naming S3 Bucket](/images/2-CreateS3Bucket/namebucket.png?featherlight=false)

- Để cho đơn giản, hãy để mặc định các mục khác và kéo xuống chọn **Create Bucket**

  ![Create S3 Bucket](/images/2-CreateS3Bucket/createbucket.png?featherlight=false)

- Hãy đợi thông báo thành công màu xanh lá để chắc chắn bucket đã được tạo

  ![Create S3 Bucket Success](/images/2-CreateS3Bucket/createsuccess.png?featherlight=false)

  {{% notice tip %}}

  Bạn có thể copy mã ARN và tên của bucket vào bảng nhớ tạm để tiện cho các bước tiếp theo.

  {{% /notice %}}

### Tạo các thư mục

1. Trở về S3 trong console

- Chọn và đi đến bucket ta mới tạo trong danh sách bucket. Bây giờ ta sẽ tạo các 'thư mục'.

- Click vào **Create Folder**

  ![Create S3 folder](/images/2-CreateS3Bucket/createfolder.png?featherlight=false)

- Nhập **source** cho tên thư mục đầu tiên.

- Để các setting như mặc định, kéo xuống chọn **Create Folder**

  ![Create S3 folder](/images/2-CreateS3Bucket/nameandcreatefolder.png?featherlight=false)

2. Làm lại quá trình tạo thư mục và tạo thêm thư mục **destination**

- Cấu trúc bucket của bạn bây giờ sẽ trông gần giống như sau:

  ![Result Bucket](/images/2-CreateS3Bucket/final.png?featherlight=false)

Tuyệt, ta đã tạo xong tài nguyên bucket S3, hãy đi đến bước tiếp theo!
