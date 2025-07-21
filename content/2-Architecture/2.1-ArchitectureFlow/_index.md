---
title : "How the architecture work?"
date :  "`r Sys.Date()`" 
weight : 1
chapter : false
pre : " <b> 2.1 </b> "
---

![Cloud Architecture](/images/2/WS1_Step.svg?featherlight=false&width=90pc)
### How the architecture work?

1. The client requests the URL of **CloudFront distribution** to get a particular website file in the **S3 bucket**.

2. **CloudFront** sends the request to **AWS WAF**. AWS WAF filters the request by using the web ACLs applied to the CloudFront distribution. 
    - If the request is determined to be valid, the flow continues. 
    - If the request is determined to be invalid, the client receives a **403 error**.

3. **CloudFront** checks its internal cache. If there is a valid key matching the incoming request, the associated value is sent back to the client as a response. If not, the flow continues.

4. **CloudFront** forwards the request to the URL of the specified **Application Load Balancer**.

5. The **Application Load Balancer** has a listener associated with a target group based on a **Lambda function**. The Application Load Balancer invokes the Lambda function.

6. The **Lambda function** connects to the S3 bucket, perform a GetObject operation on it, and returns the content as a response.



