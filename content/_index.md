---
title: "Adding watermark to image uploaded to Amazon S3 using AWS Lambda"
date: "`r Sys.Date()`"
weight: 1
chapter: false
---

# Adding watermark to new image uploaded to Amazon S3 using AWS Lambda

#### Overview

Dynamic data transformations are very common nowadays. For different applications and workloads, we often need the ability to modify the data as necessary for each use case. In this workshop, I will demonstrate how we can use AWS Lambda for a simple task such as adding a watermark to the images every time they are uploaded to an Amazon S3 bucket. This can be further expanded to every tasks that demand object modification operations before storing in S3 buckets. I will go through every step from creating all the resources needed, testing the function, and then cleaning up. Let’s get started!

![S3](/images/1-Introduce/s3.png?featherlight=false&width=5pc) ![Lambda](/images/1-Introduce/lambda.png?featherlight=false&width=5pc)

#### Content

1. [Introduction](1-introduction/)
2. [Creating the S3 bucket](2-creates3bucket/)
3. [Creating IAM role for Lambda function](3-createiamrole/)
4. [Creating and packaging Lambda function](4-packaginglambda/)
5. [Testing the function](5-testing/)
6. [Resource Cleanup](6-cleanup/)
