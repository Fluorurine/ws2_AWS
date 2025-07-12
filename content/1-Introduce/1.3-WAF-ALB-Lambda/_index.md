---
title : "WAF, Application Load Balancer & Lambda"
date :  "`r Sys.Date()`" 
weight : 3 
chapter : false
pre : " <b> 1.3 </b> "
---

### AWS Web Application Firewall (WAF)
![AWS Web Application Firewall](/images/1/waf_icon.png?featherlight=false&width=10pc)

***Amazon WAF***, stands for AWS Web Application Firewall, is a ***web application firewall that safeguards your applications from cyberattacks***. It allowing you to ***configure custom rules*** that control web traffic based on various criteria, including IP addresses, HTTP headers, body content, URLs, and protection against specific vulnerabilities like SQL injection and cross-site scripting. Additionally, AWS WAF offers prebuilt rules, bot control, and monitoring capabilities to fortify your application's security posture.

---

### Application Load Balancer (ALB)
![Application Load Balancer](/images/1/alb_icon.svg?featherlight=false&width=10pc)

An ***application load balancer (ALB)*** is a network device that acts as a ***traffic director for your applications***. It sits in front of your web servers and distributes incoming traffic among them.

An AWS application load balancer  offers several features:

- ***Smart routing***: Directs traffic based on URL, headers, or other details.

- ***HTTPS redirection***: Makes switching to secure connections automatic.
- ***TLS management***: Handles encryption/decryption, improving server performance.
- ***Server Name Indication (SNI)***: Selects the appropriate SSL certificate based on the client's hostname.
- ***Sticky sessions***: Keeps users connected to the same server by using cookies for a better experience. 
- ***Security integration***: Works with AWS WAF to protect your applications.

---
### AWS Lambda
![Application Lambda](/images/1/lambda_icon.png?featherlight=false&width=10pc)
`***AWS Lambda*** is a ***serverless compute service***, meaning you don't have to manage servers to run your code. You simply upload your code, and AWS Lambda takes care of everything else, including provisioning, scaling, and managing the underlying infrastructure.

Serverless architecture offers advantages like:

- ***Cost-effectiveness***: You only pay for the resources your code uses, eliminating idle server costs.

- ***Scalability***: Lambda can automatically scale your code to handle any amount of traffic.
- ***Faster development***: Focus on writing code without worrying about server management.

***AWS Lambda Function*** is an ***individual piece of code that runs on AWS Lambda***. You can write your function in various supported languages (like Python, Node.js, Java) and define its purpose, like processing data, responding to API requests, or triggering other AWS services.

Characteristics:
- ***Self-contained***: Each function is a complete unit with its own code and logic.

- ***Event-driven***: They are triggered by specific events, such as a file upload to S3 or an API Gateway request.