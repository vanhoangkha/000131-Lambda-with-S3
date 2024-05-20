---
title: "Package the Lambda function"
date: "`r Sys.Date()`"
weight: 3
chapter: false
pre: " <b> 4.3 </b> "
---

### Function Code

1. On your local machine:

- Create a new directory, I'll name it **`workshop1`**, you can choose any name you want.
- Inside the directory create a Python file and name it **`lambda_function.py`** for our function.
- Copy the code below and paste it inside the file you've just created:

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

- This _add_text_watermark_ function is a simple function using PIL that adds a white text watermark "SAMPLE" into the image and returns it.

- In general, the Lambda function will extract the event key and download the image with the "source/" prefix every time the user uploads an image object with this prefix in the S3 bucket. Then it will call the _add_text_watermark_ function to add a watermark and then replace the **source/** prefix with the **destination/** prefix to add the edited image to the bucket.

2. We will need to install PIL inside the directory so that the function can call methods in the library.

- Inside the same directory of your **lambda_function.py** , run the command `pip install -t . pillow`. Pip will collect the pillow library inside the current directory, your directory now should look something like this:
  ![Packaging Lambda](/images/4-PackageLambda/Package/1.png?featherlight=false)

- Now compress the directory into a single zip file by running the command `zip -r ./my_package.zip .` whereas my_package is the name of your .zip file that we'll be uploaded to our lambda function

{{% notice info %}}
Make sure again that your .zip file has a flat directory structure, with your function's handler code and all your dependency folders installed at the root.
{{% /notice %}}

3. After you got the .zip package ready on your machine, go back to the **Lambda console**

- Click on the new Lambda function on the list we've just created.
- Click on **Upload from** then **.zip file** and select the `my_package.zip` file from your machine, wait for it to upload successfully and we will move on and test the function in the next step.
