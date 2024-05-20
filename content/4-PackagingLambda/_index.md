---
title: "Creating and packaging Lambda function"
date: "`r Sys.Date()`"
weight: 4
chapter: false
pre: " <b> 4. </b> "
---

### Overview

In this step, we will start by creating the function code using Python. For the task of modifying image objects, we often need a dedicated library for image processing, we will package the function with an external library called PIL, following this documentation [Working with .zip file archives for Python Lambda functions](https://docs.aws.amazon.com/lambda/latest/dg/python-package.html).

Make sure you have your Python environment and pip on your local machine to begin. I will be using Python 3.8 on my Ubuntu machine, you will also need to note down your Python version on your machine.

For different operating systems, the concepts are basically the same but the process will be a small differences. I will demonstrate the process using Ubuntu.

### Content

1. [Create Lambda function](4.1-createlambda)
2. [Create S3 Trigger](4.2-createtrigger)
3. [Package Lambda Function](4.3-packagelambda)
