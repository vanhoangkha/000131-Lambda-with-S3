---
title: "Introduction"
date: "`r Sys.Date()`"
weight: 1
chapter: false
pre: " <b> 1. </b> "
---

## Introduction

In this workshop, I will peform a simple, basic object modification task inside AWS using AWS Lambda and Amazon S3. You will learn about the basics of AWS services such as S3, Lambda, IAM, CloudWatch. Here is the architechture that we will be following:

![Architechture](/images/1-Introduce/Architechture.png?featherlight=false)

## Solution Overview

1. [Creating the S3 bucket](2-creates3bucket/)

   In this step, we will create our S3 Bucket. Inside, there will be two folders (prefixes) for source (unprocessed) and destination (added some watermark) images for demonstration.

2. [Creating an IAM role for the Lambda function](3-createiamrole/)

   Then we will create an IAM role that has the needed permissions for the Lambda function to have access to S3 for object processing and CloudWatch Logs for writing logs.

3. [Creating and packaging the Lambda function](4-packaginglambda/)

   And we will create our Lambda function for processing the images. We will package our function with an external library for image processing and upload to AWS.

4. [Testing the function](5-testing/)

   After finishing creating the resources, we will test if the function works by uploading sample images.

5. [Resource Cleanup](6-cleanup/)

   Cleanup.

Let’s get started by logging in to the AWS console with your AWS account, it’s best to use an IAM Account with admin access, and then pick a region. I will use the ús-east-1 (N.Virginia) region in this workshop.
