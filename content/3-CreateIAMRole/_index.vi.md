---
title: "Tạo IAM role cho hàm Lambda"
date: "`r Sys.Date()`"
weight: 3
chapter: false
pre: " <b> 3. </b> "
---

### Trao các quyền cho Lambda

Hàm Lambda của chúng ta sẽ cần các quyền để tải xuống, thay đổi, và tải object lên các bucket S3. Cùng với đõ là các quyền dành cho Cloudwatch Logs để có thể viết log theo dõi các lượt thực thi.

Cách tốt nhất để giao các quyền này cho Lambda là sử dụng một **IAM Role**. Trong phần này, ta sẽ tạo IAM Role cho hàm Lambda sau này các quyền truy cập tài nguyên cần thiết.

Ta sẽ tạo một **IAM Policy** trước rồi sau đó tạo **IAM Role** để gán Policy đó vào.

### Mục lục

1. [Tạo IAM Policy](3.1-createiampolicy)

2. [Tạo IAM Role](3.2-createiamrole)
