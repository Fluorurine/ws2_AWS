---
title : "Clean up resources"
date : "`r Sys.Date()`"
weight : 2
chapter : false
pre : " <b> 4.2 </b> "
---

### Clean up resources
1. In CloudFront Management > Security, Disalbe AWS WAF protection.
![4-1](/images/4/Img4_1.png?width=90c)
2. AWS Console > CloudFront > Delete the resources.
![4-2](/images/4/Img4_2.png?width=90c)
3. AWS Console > EC2 > Load Balancer > Delete the `WS1-ALB`.
![4-3](/images/4/Img4_3.png?width=90c)
4. Next, we delete the target group mapping to our Lambda function.
![4-4](/images/4/Img4_4.png?width=90c)
5. AWS Console > Lambda > Delete `WS1_Lambda`.
![4-5](/images/4/Img4_5.png?width=90c)
6. AWS Console > S3 Bucket > Empty and delete Bucket resource (`ws1-s3 bucket`).
![4-6](/images/4/Img4_6.png?width=90c)
7. S3 Bucket deleted successfully.
![4-7](/images/4/Img4_7.png?width=90c)
8. Finally, AWS Console > VPC > My VPC > delete `WS1_VPC` that we created.
![4-8](/images/4/Img4_8.png?width=90c)
9. `WS1_VPC` has been successfully deleted. All the subnet and security group attach to it follows.
![4-9](/images/4/Img4_9.png?width=90c)

