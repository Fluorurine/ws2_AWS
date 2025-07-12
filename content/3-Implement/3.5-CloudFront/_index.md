---
title : "Create CloudFront Origin"
date : "`r Sys.Date()`"
weight : 5
chapter : false
pre : " <b> 3.5 </b> "
---

### Create CloudFront Origin
1. Create ***Amazon CloudFront*** distribution:
- In ***AWS Console*** > Search ***CloudFront*** > CloudFront
![3-47](/images/3/Img3_47.png?width=90c)
- Choose ***"Create a CloudFront distribution"***.
![3-48](/images/3/Img3_48.png?width=90c)
2. Add Application Load Balancer as CloudFront origin.
![3-55](/images/3/Img3_55.png?width=90c)
3. Set cache policy as you wish:
![3-56](/images/3/Img3_56.png?width=90c)
4. Enalbe WAF in CloudFront with core protection:
![3-57](/images/3/Img3_57.png?width=90c)
5. Choose suitable price class and create cloudfront distribution.
![3-58](/images/3/Img3_58.png?width=90c)
6. CloudFront distribution created successfully. Remember the origin as we need it to test if it working correctly.
![3-59](/images/3/Img3_59.png?width=90c)
