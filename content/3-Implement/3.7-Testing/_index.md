---
title : "Testing the Result"
date : "`r Sys.Date()`"
weight : 7
chapter : false
pre : " <b> 3.7 </b> "
---

### What happen to other CloudFront origin as Application Load Balancer? 
In the original diagram, there is two Application Load Banlancer. of different region. 
![3-67](/images/1/WS1.svg?width=90pc)
To achive this, we do not configure in CloudFront distribution origin. Instead, we configure it in Amazon Route 53 to route our traffic to the right AZ origin by using ***"Geolocation Routing"***.
More information about it can find here [AWS Document](https://docs.aws.amazon.com/Route53/latest/DeveloperGuide/routing-policy-geo.html)

### Fetch diffrent resources in CloudFront
If we can fetch the static resources in S3 bucket that mean our set up is working correctly. (Using two images provided in S3 bucket).

We fetch `Img3_A.png` and `Img3_B.png` from CloudFront origin.
![3-67](/images/3/Img3_67.png?width=90c)
![3-68](/images/3/Img3_68.png?width=90c) 