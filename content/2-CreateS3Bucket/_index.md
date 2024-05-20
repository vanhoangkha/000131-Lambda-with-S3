---
title: "Creating the S3 bucket"
date: "`r Sys.Date()`"
weight: 2
chapter: false
pre: " <b> 2. </b> "
---

### Overview

In this section, we will start creating our bucket for testing, we will add two prefixes named **source/** and **destination/** in the bucket to act as folders inside the bucket for demonstration.

The **source/** folder will be for storing the source, unedited images that we've uploaded, and the **destination/** folder will store images with a watermark after modification.

{{% notice info %}}
Amazon S3 has a **flat structure** instead of a hierarchy like you would see in a file system. However, for organizational simplicity, the Amazon S3 console supports the folder concept as a means of grouping objects by using a shared name prefix for the grouped objects.
{{% /notice %}}

### Creating the bucket

1. In the AWS console home page:

- Navigate to the search bar, type S3, and click on the service.

  ![Go to S3](/images/2-CreateS3Bucket/start.png?featherlight=false)

- In the S3 console click on **Create Bucket**

  ![Create bucket](/images/2-CreateS3Bucket/startcreate.png?featherlight=false)

2. In the create bucket window:

- Choose your preferred region for our S3 Bucket
- Enter the name for the S3 bucket, make sure it follows the bucket naming scheme and is globally unique, I will name my bucket
  **`lambda-watermark-bucket-_randomnumber_`**

  ![Naming S3 Bucket](/images/2-CreateS3Bucket/namebucket.png?featherlight=false)

- We can leave the settings as default for simplicity then scroll down and click on **Create Bucket**

  ![Create S3 Bucket](/images/2-CreateS3Bucket/createbucket.png?featherlight=false)

- Wait for the success message from the console to make sure the bucket is created successfully.

  ![Create S3 Bucket Success](/images/2-CreateS3Bucket/createsuccess.png?featherlight=false)

  {{% notice tip %}}
  You can copy the bucket name and ARN and put it in the clipboard or somewhere for later steps.
  {{% /notice %}}

### Creating the folders

1. Back in S3 console:

- Go to the bucket we've just created by clicking on it from the bucket list. Now we can start creating folders
- Click on **Create Folder**

  ![Create S3 folder](/images/2-CreateS3Bucket/createfolder.png?featherlight=false)

- Enter "source" as the name for the folder.
- We can leave the settings as default and then click on **Create Folder**

  ![Create S3 folder](/images/2-CreateS3Bucket/nameandcreatefolder.png?featherlight=false)

2. Repeat the creating folder process for our "destination" folder, it will store images with a watermark after modification.

- Go back and your bucket structure will look something like this:

  ![Result Bucket](/images/2-CreateS3Bucket/final.png?featherlight=false)

Great, now you have created the S3 bucket successfully! Move on to the next step.
