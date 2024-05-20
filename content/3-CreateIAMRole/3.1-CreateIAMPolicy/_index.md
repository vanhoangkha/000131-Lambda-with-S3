---
title: "Create IAM Policy"
date: "`r Sys.Date()`"
weight: 1
chapter: false
pre: " <b> 3.1 </b> "
---

### Create IAM Policy

1. Access the **AWS Management Console** interface:

- Look for **IAM** and click on the service to go to the IAM Console.

2. Within the **IAM** console interface:

- On the right menu, locate and click on **Policies**
- Then click on **Create Policy**

  ![Create Policy](/images/3-CreateIAMRole/startcreatepolicy.png?featherlight=false)

3. Follow these steps to create an IAM Policy that allows access to CloudWatch Logs and the S3 bucket we've created:

- On the **Specify Permissions** window, choose **JSON** for our policy editor.

  ![Create Policy](/images/3-CreateIAMRole/startjson.png?featherlight=false)

  {{% notice note %}}
  You can also use the Visual Editor to specify permission but it is usually prone to mistakes, so review carefully before creating policy.
  {{% /notice %}}

- Copy the JSON policy below to the clipboard.

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

- Replace **YOUR-BUCKET-NAME** with the actual name of your bucket that you've copied before.

  ![Create Policy](/images/3-CreateIAMRole/pastejson.png?featherlight=false)

- Click on **Next**
- Enter the policy name as **`LambdaWatermarkS3`**
- Review the policy permission and click on **Create policy**

  ![Create Policy](/images/3-CreateIAMRole/finishpolicy.png?featherlight=false)

4. Completed the process of creating the **IAM Policy**

- In the policy list, filter by name **`LambdaWatermarkS3`** or by type **Customer managed**, you should find the new policy has been created

  ![Create Policy](/images/3-CreateIAMRole/donepolicy.png?featherlight=false)

Next, let's create an IAM Role and attach this policy.
