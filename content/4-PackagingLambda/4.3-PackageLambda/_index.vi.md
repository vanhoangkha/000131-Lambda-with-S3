---
title: "Đóng gói hàm Lambda"
date: "`r Sys.Date()`"
weight: 3
chapter: false
pre: " <b> 4.3 </b> "
---

### Viết code cho hàm Lambda

1. Trong máy tính cục bộ của bạn:

- Tạo một thư mục mới, tôi sẽ đặt tên là **`workshop1`**, bạn có thể đặt tên bất kỳ.

- Vào trong thư mục và tạo một tệp Python, đặt tên là **`lambda_function.py`** chứa code cho hàm Lambda.

- Sao chép đoạn code dưới đây và dán vào file **`lambda_function.py`** của bạn.

  ```python
  from PIL import Image, ImageDraw, ImageFont
  import boto3
  import os

  s3 = boto3.client('s3')

  def add_text_watermark(image_path):
      watermark_text = "SAMPLE"
      image = Image.open(image_path)
      draw = ImageDraw.Draw(image)

      w, h = image.size
      x, y = int(w / 2), int(h / 2)

      font = ImageFont.load_default(size=30)

      draw.text((x, y), watermark_text, fill=(255, 255, 255), font=font, anchor='ms')

      image.save(image_path)
      image.close()

  def lambda_handler(event, context):
      # Extract the bucket name and key from the event
      bucket = event['Records'][0]['s3']['bucket']['name']
      key = event['Records'][0]['s3']['object']['key']

      # Define the download path in the Lambda temporary directory and the upload path
      download_path = '/tmp/' + os.path.basename(key)
      upload_key = 'destination/' + os.path.basename(key)  # Save watermarked images in 'destination' folder

      # Download the image from the 'source' folder
      source_key = 'source/' + os.path.basename(key)
      s3.download_file(bucket, source_key, download_path)

      # Add a watermark to the image
      add_text_watermark(download_path)

      # Upload the watermarked image to the 'destination' folder
      s3.upload_file(download_path, bucket, upload_key)

      # Clean up the temporary file
      os.remove(download_path)

      return {
          'statusCode': 200,
          'body': 'Watermark added successfully!'
      }

  ```

- Hàm _add_text_watermark_ là một hàm đơn giản sử dụng thư viện PIL để thêm watermark trắng "SAMPLE" vào giữa ảnh và trả về ảnh mới.
- Tổng quan cho đoạn code trên, hàm Lambda sẽ lấy key và tải object xuống môi trường chạy từ event nhận được từ trigger là một object với prefix `source/` mỗi khi người dùng thêm tệp vào thư mục này trong bucket S3. Sau đó gọi hàm _add_text_watermark_ để thêm watermark và sau đó upload lại lên thư mục **destination/**.

2. Ta sẽ cài đặt PIL bằng pip vào chính thư mục chứa hàm Lambda để hàm có thể gọi thư viện này:

- Trong terminal của thư mục chứa tệp **lambda_function.py**, chạy lệnh `pip install --target . pillow`. Pip sẽ tải các thư viện cần thiết chỉ trong thư mục này, cấu trúc thư mục trông sẽ như sau:

![Packaging Lambda](/images/4-PackageLambda/Package/1.png?featherlight=false)

- Sau đó đóng gói cả thư mục này vào một tệp .zip bằng cách chạy lệnh `zip -r ./my_package.zip .` trong đó _my_package_ là tên của tệp .zip chứa đầy đủ các tệp sẵn sàng upload để chạy trên Lambda.

{{% notice info %}}

Hãy chắc chắn rằng trong file .zip phải có cấu trúc phẳng, với code hàm lambda và các thư viện đã tải cùng nằm trong gốc của thư mục.

{{% /notice %}}

3. Sau khi xong việc tạo file .zip, ta quay trở lại giao diện Lambda trong **AWS console**

- Nhấp chọn vào hàm Lambda ta tạo trước đó **`WatermarkS3Upload`**.

- Chọn mục **Upload from** sau đó chọn **.zip file**, cửa sổ chọn tệp sẽ hiện lên, tìm kiếm và chọn tệp `my_package.zip` từ máy của bạn , đợi cho việc tải lên thành công, sau đó hãy đến bước tiếp theo.
