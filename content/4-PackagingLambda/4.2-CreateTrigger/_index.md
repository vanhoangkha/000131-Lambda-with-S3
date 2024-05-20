---
title: "Create the S3 Trigger"
date: "`r Sys.Date()`"
weight: 2
chapter: false
pre: " <b> 4.2 </b> "
---

### Add a trigger for the Lambda function

1. On the new Lambda function console

- Look for **Add Trigger** and click on it.
  ![Create Lambda Function](/images/4-PackageLambda/Create/trigger1.png?featherlight=false)

2. Within the **Add Trigger** interface:

- Select **S3** as the source from the dropdown
  ![Create Lambda Function](/images/4-PackageLambda/Create/trigger2.png?featherlight=false)

- Next, in **Bucket** choose the bucket we have created before from the dropdown.
- For **Event types** select **All object create events**
- We will listen to trigger on the object created on the prefix "source/" so type "source/" for **Prefix**
- Because we've purposely created two prefixes and listened to events triggered from the **source/** prefix, we will avoid repetitive Lambda calls for object creation by making sure the Lambda function will post the object to the **destination/** prefix in the S3 bucket.
- Once you've done configuring, click on **Add**

  ![Create Lambda Function](/images/4-PackageLambda/Create/trigger3.png?featherlight=false)

- We've successfully created an S3 trigger for our function
  ![Create Lambda Function](/images/4-PackageLambda/Create/trigger4.png?featherlight=false)

Great! Now we will start implementing and packaging the function.
