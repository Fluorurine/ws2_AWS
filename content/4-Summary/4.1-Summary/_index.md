---
title : "Summary"
date : "`r Sys.Date()`"
weight : 1
chapter : false
pre : " <b> 4.1 </b> "
---

### What we can improve ?
- Implement Amazon Route 53 and Geolocation Routing.
- To automate the deployment of static content using this approach, create CI/CD pipelines to update the Amazon S3 buckets that host websites.
- Make sure to properly define the cache for the CloudFront distribution.
- Implement WAF security rules.
- Upgrade ALB connection to HTTPS.
### Related Resources
- Optimizing caching and availability [CloudFront documentation](https://docs.aws.amazon.com/AmazonCloudFront/latest/DeveloperGuide/ConfiguringCaching.html)
- Lambda functions as targets [Elastic Load Balancing documentation](https://docs.aws.amazon.com/elasticloadbalancing/latest/application/lambda-functions.html)
- Lambda quotas [Lambda documentation](https://docs.aws.amazon.com/lambda/latest/dg/gettingstarted-limits.html)

AWS service websites:
- [Application Load Balancer](https://aws.amazon.com/es/elasticloadbalancing/application-load-balancer/)
- [Lambda](https://aws.amazon.com/en/lambda/)
- [CloudFront](https://aws.amazon.com/en/cloudfront/)
- [Amazon S3](https://aws.amazon.com/en/s3/)
- [AWS WAF](https://aws.amazon.com/en/waf/)
- [Amazon VPC](https://aws.amazon.com/en/vpc/)