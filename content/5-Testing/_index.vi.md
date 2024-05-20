---
title: "Test hoạt động"
date: "`r Sys.Date()`"
weight: 5
chapter: false
pre: " <b> 5. </b> "
---

### Test hàm Lambda

Trong trang quản lý AWS Lambda có hỗ trợ chạy thử các test với các template, nhưng với quá trình này, việc test khá đơn giản nên ta có thể tự tải tệp lên và kiểm tra kết quả trong các thư mục. Ta sẽ tải thử một sổ tệp vào thư mục prefix
**source/** và xem kết quả trong **destination/**

Tôi đã chuẩn bị một vài tệp ảnh _.jpg_ trong máy. Chúng ta có thể tải lên bất kỳ loại file ảnh nào PIL hỗ trợ, hãy nhớ rằng các lỗi thực thi (bao gồm định dạng tệp không hỗ trợ) sẽ đều được ghi lại trong một nhóm CloudWatch Log.

1. Trở về **AWS Console**, tìm S3 và chọn dịch vụ để đi tới.

![Go to S3](/images/2-CreateS3Bucket/start.png?featherlight=false)

- Tìm kiếm và chọn bucket ta đã tạo trong project này

  ![Go to S3](/images/5-Test/1.png?featherlight=false)

- Click vào thư mục **source/**.

  ![Go to S3](/images/5-Test/2.png?featherlight=false)

- Chọn **Upload**

  ![Go to S3](/images/5-Test/3.png?featherlight=false)

- Trong cửa sổ **Upload**, chọn **Add files**

  ![Go to S3](/images/5-Test/4.png?featherlight=false)

- Chọn một hoặc nhiều ảnh bạn muốn và bấm **Upload**. Đợi quá trình tải tệp mới thành công.

2. Trở về trang bucket trước đó.

- Bạn kiểm tra ảnh bằng cách chọn vào thư mục **destination/**, sẽ có ảnh tải lên với tên giống với ảnh bạn đã chọn.

- Chọn vào ảnh đó và bấm **Download**, bạn mở ảnh sẽ có ảnh cũ nhưng bây giờ đã có thêm watermark "SAMPLE" màu trắng ở chính giữa

Ảnh tải lên thư mục **source/**

![Before Image](/images/5-Test/b4.png?featherlight=false)

Ảnh sau khi hàm Lambda đã chạy, trong thư mục **destination/**

![After Image](/images/5-Test/after.png?featherlight=false)

### Kiểm tra log

Một điều nữa bạn nên chú ý chính là việc xem lại log các lần thực thi hàm Lambda.

1. Trở về **AWS Console**, tìm CloudWatch và click để đi đến trang dịch vụ CloudWatch.

![Go to CW](/images/5-Test/5.png?featherlight=false)

2. Trong menu bên trái, mở rộng mục **Log** và chọn **Log group**

- Bạn sẽ tìm thấy một nhóm log bắt đầu bởi **aws/lambda/** và sau đó là tên hàm Lambda của chúng ta **`WatermarkS3Upload`** nếu đã thực hiện thành công.
  ![Go to CW](/images/5-Test/6.png?featherlight=false)

- Hãy thử chọn thư mục log mới nhất và xem các log đã được ghi lại.

  ![Go to CW](/images/5-Test/7.png?featherlight=false)

- Log chạy hàm Lambda

  ![Go to CW](/images/5-Test/8.png?featherlight=false)

Vậy là bạn đã gần như hoàn thành bài workshop này, bây giờ chúng ta sẽ nên dọn dẹp các tài nguyên, trả tài khoản về trạng thái cũ để tránh các khoản phí không mong muốn.
