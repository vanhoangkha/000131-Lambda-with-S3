---
title: "Create IAM Role"
date: "`r Sys.Date()`"
weight: 2
chapter: false
pre: " <b> 3.2 </b> "
---

### Create IAM Role

1. Back to the IAM Console:

- On the right menu, locate and click on **Roles**
- Then click on **Create Role**

  ![Create Role](/images/3-CreateIAMRole/startcreaterole.png?featherlight=false)

2. In the **Create role** Interface:

- For section **Select trusted entity** choose **AWS Service**.
- For **Use Case** select **Lambda** from the dropdown.

  ![Create Role](/images/3-CreateIAMRole/createrole1.png?featherlight=false)

3. Attach **IAM Policy**:

- In the **Add Permission** section, filter the policies just like we did before and select **`LambdaWatermarkS3`** to attach.
- Click on **Next**
  ![Create Role](/images/3-CreateIAMRole/createrole2.png?featherlight=false)

4. Name and create **IAM Role**

- Next, name the role as **`LambdaWatermarkS3Role`**
  ![Create Role](/images/3-CreateIAMRole/createrole3.png?featherlight=false)
- Review and click on **Create Role**

  ![Create Role](/images/3-CreateIAMRole/createrole4.png?featherlight=false)

5. Finish Creating **IAM Role**

   ![Create Role](/images/3-CreateIAMRole/finishrole.png?featherlight=false)

Great, now let's go ahead and create our Lambda function.
