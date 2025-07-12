---
title : "Create Amazon WAF"
date : "`r Sys.Date()`"
weight : 6
chapter : false
pre : " <b> 3.6 </b> "
---

## Configure Amazon Web Application Firewall
1. In previous section, we created ***WAF*** with CloudFront, however, the WAF is still at ***core protection*** mode.
- We can leverage the power of Amazon WAF to protect our origin.
![3-60](/images/3/Img3_60.png?width=90c)
- When we Enalbe CloudFront WAF for core protection we actually create a WAF. To view it in detail we follow:
![3-61](/images/3/Img3_61.png?width=90c)
![3-63](/images/3/Img3_62.png?width=90c)
2. This is detail overview of Amazon WAF attached to CloudFront.
- We can use rule tab to add more rule to our WAF.
![3-64](/images/3/Img3_64.png?width=90c)
3. Add rule and tweak it based on industrial requirement:
![3-65](/images/3/Img3_65.png?width=90c)
![3-66](/images/3/Img3_65.png?width=90c)