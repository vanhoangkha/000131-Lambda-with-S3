---
title: "Testing the function"
date: "`r Sys.Date()`"
weight: 5
chapter: false
pre: " <b> 5. </b> "
---

### Testing the function

AWS Lambda supports function testing with event creation inside the console, but with this simple process, we can just test the function by uploading some images to the **source** folder in our S3 bucket and seeing the result in the **destination** folder.

I've prepared some _.jpg_ images on my machine. You can put in any type of image that the PIL library supports, any error (including incompatible image file type) in the execution of the Lambda function will be logged into a CloudWatch Log group.

1. From the AWS console, go back to S3.

   ![Go to S3](/images/2-CreateS3Bucket/start.png?featherlight=false)

- Locate and select the bucket that we've created in this workshop.

  ![Go to S3](/images/5-Test/1.png?featherlight=false)

- Locate and click on the **source/** folder to go inside the folder
  ![Go to S3](/images/5-Test/2.png?featherlight=false)
- Choose **Upload**
  ![Go to S3](/images/5-Test/3.png?featherlight=false)
- In the **Upload** window, select **Add files**
  ![Go to S3](/images/5-Test/4.png?featherlight=false)
- Choose an image file or multiple image files that you want to upload in the file by choosing in the popup window

2. Go back to the bucket

- You can just check the result images by clicking on the **destination** folder, the images should have the same name as you've uploaded.
- Select the image object to view details
- Click **Download**, now you can open the image and it should have the watermark inside.

Image in the source folder
![Before Image](/images/5-Test/b4.png?featherlight=false)

After Lambda invocation, in the destination folder
![After Image](/images/5-Test/after.png?featherlight=false)

### Checking the logs

One more thing, you should also take a look at the log files that have been created for every Lambda invocation to inspect the operation.

1. Look for CloudWatch in the search bar of your AWS Console
   ![Go to CW](/images/5-Test/5.png?featherlight=false)

2. In the left menu, expand Logs then select Log group

- You should see the Log group with the prefix **aws/lambda/** plus our function name **`WatermarkS3Upload`** if you completed all the previous steps. Click on it
  ![Go to CW](/images/5-Test/6.png?featherlight=false)

- Select the latest log group and expand the logs to explore.
  ![Go to CW](/images/5-Test/7.png?featherlight=false)
- My function logs
  ![Go to CW](/images/5-Test/8.png?featherlight=false)

That's it, you've basically finished this workshop. Now let's go ahead and delete the resources to restore your account to the state it was in to avoid unwanted charges.
