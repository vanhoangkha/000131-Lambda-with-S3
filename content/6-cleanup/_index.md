---
title: "Clean up resources"
date: "`r Sys.Date()`"
weight: 6
chapter: false
pre: " <b> 6. </b> "
---

### Clean up resources

We will proceed to delete the resources in the following order:

### Delete the Lambda function

- Access the AWS Lambda console.
- Select the function we've created.
- Expand Action and click Delete

  ![Delete Lambda](/images/6-Cleanup/lambda_1.png?featherlight=false)

- Confirm deletion.
  ![Delete Lambda](/images/6-Cleanup/lambda_2.png?featherlight=false)

### Delete the S3 Bucket

- Access S3 in the **AWS console**.
- Select the bucket we've created.
- Click **Empty**

  ![Delete bucket](/images/6-Cleanup/s3_1.png?featherlight=false)

- Confirm object deletion
  ![Delete bucket](/images/6-Cleanup/s3_2.png?featherlight=false)

- Go back to the bucket
- Choose **Delete**
  ![Delete bucket](/images/6-Cleanup/s3_3.png?featherlight=false)

- Confirm bucket deletion
  ![Delete bucket](/images/6-Cleanup/s3_4.png?featherlight=false)

### Delete the IAM Policy

- Access IAM in the **AWS console**.
- On the left menu, click **Policies**
- Filter to select the Policy we've created **`LambdaWatermarkS3`**
- Click **Delele**
  ![Delete IAM policy](/images/6-Cleanup/iam_pol1.png?featherlight=false)

- Confirm deletion
  ![Delete IAM policy](/images/6-Cleanup/iam_pol2.png?featherlight=false)

### Delete the IAM Role

- Back to IAM in the **AWS console**.
- On the left menu, click **Roles**
- Filter to select the IAM role we've created **`LambdaWatermarkS3Role`**
- Click **Delele**
  ![Delete IAM role](/images/6-Cleanup/iam_rol1.png?featherlight=false)

- Confirm deletion
  ![Delete IAM role](/images/6-Cleanup/iam_rol2.png?featherlight=false)

Thank you for taking your time to finish this workshop!!!
