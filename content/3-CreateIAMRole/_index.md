---
title: "Creating an IAM role for Lambda function"
date: "`r Sys.Date()`"
weight: 3
chapter: false
pre: " <b> 3. </b> "
---

### Lambda Permissions

Our Lambda function will need permissions to be able to download, modify, and upload the image in the S3 bucket. Writing logs in Cloudwatch Logs permission is also a necessary task for logging and monitoring each execution.

The best way to do it is by giving the Lambda function an IAM Role. In this section, I'll show you how to give the Lambda function which will be created later the permissions needed for the workshop task, using an IAM Role.

We'll start by creating a new custom IAM Policy then after creating a new IAM Role and attach it to the managed policy.

### Content

1. [Create IAM Policy](3.1-createiampolicy)
2. [Create IAM Role](3.2-createiamrole)
