---
title : "Introduction"
date :  "`r Sys.Date()`" 
weight : 1 
chapter : false
pre : " <b> 1. </b> "
---

### Introduction

This architecture is inspired by [This AWS Prescriptive Guidance](https://docs.aws.amazon.com/prescriptive-guidance/latest/patterns/serve-static-content-in-an-amazon-s3-bucket-through-a-vpc-by-using-amazon-cloudfront.html) ideal.

When you serve static content that is hosted on Amazon Web Services (AWS), the recommended approach is to use an Amazon Simple Storage Service (S3) bucket as the origin and use Amazon CloudFront to distribute the content. There are two primary benefits of this solution. The first is the convenience of caching static content at edge locations. The second is that you can define web access control lists (web ACLs) for the CloudFront distribution, which helps you secure requests to the content with minimal configuration and administrative overhead.

However, there is a common architectural limitation to the standard, recommended approach. In some environments, you want virtual firewall appliances deployed in a virtual private cloud (VPC) to inspect all content, including static content. The standard approach doesn’t route traffic through the VPC for inspection. This pattern provides an alternative architectural solution. You still use a CloudFront distribution to serve static content in an S3 bucket, but the traffic is routed through the VPC by using an Application Load Balancer. An AWS Lambda function then retrieves and returns the content from the S3 bucket.

![Serve static content through VPC with CloudFront](/images/1/WS1.svg?featherlight=false&width=90pc "Serve static content through VPC with CloudFront")
### Contents

- [What is Amazon CloudFront ?](1.1-CloudFront/)
- [Amazon S3](1.2-AmazonS3/)
- [WAF-ALB-Lambda](1.3-WAF-ALB-Lambda/)

In the following sections, we will delve into the fundamental concepts of VPC.
