---
title : "Create Application Load Balancer"
date : "`r Sys.Date()`"
weight : 4
chapter : false
pre : " <b> 3.4 </b> "
---

## Create Application Load Balancer (ALB)
1. Go to ***AWS Console*** > ***EC2***and choose the EC2 interface.
![3-30](/images/3/Img3_30.png?width=90c)
2. Scoll down to Load Balancing Category then click on Load Balancers. Then choose Create Load Balancer.
![3-32](/images/3/Img3_32.png?width=90c)
3. In this workshop we will choose ***ALB***:
![3-33](/images/3/Img3_33.png?width=90c)
4. The Application Load Balancer type is ***internet facing ALB***. Next, name it `WS1_ALB`:
![3-34](/images/3/Img3_34.png?width=90c)    
5. Map ALB to `WS1_VPC` VPC, and two public subnet:
![3-37](/images/3/Img3_37.png?width=90c)    

{{% notice note %}}
Internet Facing Load Balancer has a publicly accessible address and forwards those requests to healthy servers behind the scenes. 
{{% /notice %}}

For Internet facing load balancer to work we need an Public Subnet with Internet Access.


6. To make this simple we will choose ***HTTP Listener*** for ALB then associate that listener with Lambda target group that we create from step ***3.4***.
![3-38](/images/3/Img3_38.png?width=90c)
7. Choose suitable security group for our ALB to receive traffic from internet.
![3-52](/images/3/Img3_52.png?width=90c)
7. Review and create ALB.
![3-39](/images/3/Img3_39.png?width=90c)
![3-40](/images/3/Img3_40.png?width=90c)
