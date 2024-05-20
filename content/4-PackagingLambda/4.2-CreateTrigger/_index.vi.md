---
title: "Tạo trigger S3"
date: "`r Sys.Date()`"
weight: 2
chapter: false
pre: " <b> 4.2 </b> "
---

### Tạo một **trigger** cho hàm Lambda

1. Trong cửa sổ hàm Lamda mới tạo thành công

- Tìm mục **Add Trigger** và chọn nó.

  ![Create Lambda Function](/images/4-PackageLambda/Create/trigger1.png?featherlight=false)

2. Trong giao diện **Add Trigger**:

- Chọn **S3** là nguồn trong phần **Source**

  ![Create Lambda Function](/images/4-PackageLambda/Create/trigger2.png?featherlight=false)

- Tiếp theo, trong phần **Bucket** hiện lên, chọn bucket ta đã tạo trước đó trong danh sách thả xuống.

- Mục **Event types** chọn **All object create events**

- Chúng ta sẽ cài đặt để lắng nghe các sự kiện tạo object trong thư mục prefix **source/**, hãy điền `source/` trong mục **Prefix**

- Chúng ta chủ động tạo hai prefix khác nhau trước đó nên sẽ tránh được việc các hàm Lambda bị gọi lặp đi lặp lại khi chính nó cũng upload object, nhưng giờ đây sẽ tải lên với prefix **destination/** .

- Kiểm tra lại và chọn **Add**

  ![Create Lambda Function](/images/4-PackageLambda/Create/trigger3.png?featherlight=false)

- Tạo thành công trigger S3 cho hàm Lambda.

  ![Create Lambda Function](/images/4-PackageLambda/Create/trigger4.png?featherlight=false)

Tuyệt vời! Bây giờ ta sẽ viết code cho hàm Lambda và đóng gói chung với thư viện cần thiết và tải lên Lambda.
