---
title : "Pros and Cons"
date :  "`r Sys.Date()`" 
weight : 2
chapter : false
pre : " <b> 2.2 </b> "
---

### Benefits
- The convenience of caching static content at edge locations.

- You can define web access control lists (web ACLs) for the CloudFront distribution (using WAF), which helps you secure requests to the content with minimal configuration and administrative overhead.

- The traffic is routed through the VPC for inspection. -> Very flexible when handing logic between VPC resource and S3 static content.

- Security.

### Limitations

- The resources in this pattern must be in a single AWS Region, but they can be provisioned in different AWS accounts.

- Limits apply to the maximum request and response size that the Lambda function can receive and send, respectively. For more information, see Limits in [Lambda functions as targets](https://docs.aws.amazon.com/elasticloadbalancing/latest/application/lambda-functions.html) (Elastic Load Balancing documentation).


 ***It's important to find a good balance between performance, scalability, security, and cost-effectiveness when using this approach.*** Despite the high scalability of Lambda, if the  number of concurrent Lambda invocations exceeds the maximum quota, some requests are throttled. 
 
 For more information, see [Lambda quotas](https://docs.aws.amazon.com/lambda/latest/dg/gettingstarted-limits.html). 
 
 You also need to consider pricing when using Lambda. ***To minimize Lambda invocations, make sure that you properly define the cache for the CloudFront distribution***. See Optimizing caching and availability ([CloudFront documentation](https://docs.aws.amazon.com/AmazonCloudFront/latest/DeveloperGuide/ConfiguringCaching.html)).