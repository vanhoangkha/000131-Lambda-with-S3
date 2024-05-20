---
title: "Create a Lambda Function"
date: "`r Sys.Date()`"
weight: 1
chapter: false
pre: " <b> 4.1 </b> "
---

### Create a Lambda function

1. Access the **AWS Management Console** interface:

- Look for **Lambda** and click on the service icon to go to the Lambda Console.
  ![Create Lambda Function](/images/4-PackageLambda/Create/start.png?featherlight=false)

2. Within the **Lambda** console interface:

- Click on **Create a function**
  ![Create Lambda Function](/images/4-PackageLambda/Create/create1.png?featherlight=false)

3. On the **Create function** window:

- Choose **Author from scratch** as the method

- For **Basic information**, enter the name of the Lambda function as **`WatermarkS3Upload`**
- For **Runtime**, choose the version of your Python environment.

  ![Create Lambda Function](/images/4-PackageLambda/Create/create2.png?featherlight=false)

  {{% notice warning %}}
  Make sure you got the runtime version the same as your environment, otherwise the function may not work.
  {{% /notice %}}

- Next, expand **Change default execution role**, select **Use an existing role**

- From the dropdown, select the IAM Role we have created in the previous step **`LambdaWatermarkS3Role`**

- We now can move on by clicking **Create function**

  ![Create Lambda Function](/images/4-PackageLambda/Create/create3.png?featherlight=false)

- Successfully created function
  ![Create Lambda Function](/images/4-PackageLambda/Create/create4.png?featherlight=false)

Next up, we're going to create the trigger for our lambda function
