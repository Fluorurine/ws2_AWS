---
title : "Create VPC and Subnet"
date : "`r Sys.Date()`"
weight : 2
chapter : false
pre : " <b> 3.2 </b> "
---
We create a VPC and two public subnet in it. Those subnet is where our Application Load Balancer sit.
### Create VPC
1. Access the ***AWS Management Console*** interface:
   - Locate and click on ***VPC***
   - Choose ***VPC***

![3-1](/images/3/Img3_1.png?width=90c)

2. Within the VPC interface:
   - Select **Your VPC**
   - Click on **Create VPC**
   
![3-2](/images/3/Img3_2.png?width=90c)

3. Setting for the VPC:
   - Choose Resource and select VPC only
   - Enter Name tag as `WS1-VPC`
   - Set IPv4 CIDR to `10.10.0.0/16`

![3-3](/images/3/Img3_3.png?width=90c)

4. After the VPC is created, we edit the VPC setting to enable DNS hostname.
![3-14](/images/3/Img3_14.png?width=90c)
![3-15](/images/3/Img3_15.png?width=90c)

### Create subnet
1. We will create a public subnet for the application load balancer to sits. To do this go to VPC interface:
![3-16](/images/3/Img3_16.png?width=90c)
2. Attach our ***public sunbet*** to VPC
![3-17](/images/3/Img3_17.png?width=90c)
3. Procced with IP CIDR block is `10.10.1.0/24`. Other fields can leave at their default value.
![3-18](/images/3/Img3_18.png?width=90c)
4. On the public subnet we will want it to assign the IP address for us:
![3-19](/images/3/Img3_19.png?width=90c)
![3-20](/images/3/Img3_20.png?width=90c)
5. Next we create **internet gateway** so that every component in our VPC can route traffic through internet:
![3-21](/images/3/Img3_21.png?width=90c)
![3-22](/images/3/Img3_22.png?width=90c)
6. After we created the ***internet gateway***, it have ***"Detatched"*** state (1). Attach it to public subnet:
![3-23](/images/3/Img3_23.png?width=90c)
![3-24](/images/3/Img3_24.png?width=90c)
7. Lastly, we make ***route table ***so that our component in public subnet can connect to internet. Back to VPC interface:
![3-25](/images/3/Img3_25.png?width=90c)
   We attach rotue table to our VPC and name it as `WS1_PulicRouteTable`:
![3-26](/images/3/Img3_26.png?width=90c)
   Edit route table:
![3-27](/images/3/Img3_27.png?width=90c)  
   Click "Add route" and add route to route all traffic (`0.0.0.0/0`) to Internet Gateway that we created.
![3-28](/images/3/Img3_28.png?width=90c) 
![3-29](/images/3/Img3_29.png?width=90c)
   Finally, attach route table to our Public Subnet.
![3-35](/images/3/Img3_35.png?width=90c) 
![3-36](/images/3/Img3_36.png?width=90c)
{{% notice note %}}
Internet Facing Load Balancer require at least two public facing subnet for high availbility. -> Create another public subnet follow the same procedure with CIDR 10.10.2.0/24
{{% /notice %}}
### Create Security Group
For our Application Load Balancer to work, we need to create a security group to allow traffic target it. (Inbound Rule)
In the VPC Interface > Security Section in the left menu > Security Groups > Create security group
![3-49](/images/3/Img3_49.png?width=90c)
Configure the security group as follow:
![3-50](/images/3/Img3_50.png?width=90c)
![3-51](/images/3/Img3_51.png?width=90c)
{{% notice note %}}
Default security group only allow outbound traffic which not allow other on internet to communicate to our Applicaiton Load Balancer.
{{% /notice %}}
With that our VPC and subnet are ready for a public facing Load Balancer. 
