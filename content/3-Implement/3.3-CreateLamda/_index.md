---
title : "Lambda function"
date : "`r Sys.Date()`"
weight : 3
chapter : false
pre : " <b> 3.3 </b> "
---

### Create Lambda Function 
1. Access the ***AWS Management Console*** interface:
   - Locate and click on ***Lambda***
   - Choose ***Lambda***

![3-4](/images/3/Img3_4.png?width=90c)

2. If you currently don't have any lambda function. Choose ***"Create a function"***.
![3-5](/images/3/Img3_5.png?width=90c)

3. Create a Lambda function with a name. Other fields can be left at their default values
![3-6](/images/3/Img3_6.png?width=90c)
{{% notice note %}}
There is a different module import syntax between Node 16.x.x with later version. For this workshop we will stick with Node 16.x.x.
{{% /notice %}}

4. Using this code to handle the request from ALB to our Lambda function:
```javascript
/**

 * This is an AWS Lambda function created for demonstration purposes.

 * It retrieves static assets from a defined Amazon S3 bucket.

 * To make the content available through a URL, use an Application Load Balancer with a Lambda integration.
 * 
 * Set the S3_BUCKET environment variable in the Lambda function definition.
 */
// Import the AWS SDK for interacting with AWS services
var AWS = require('aws-sdk');
// Define the Lambda function handler
exports.handler = function(event, context, callback) {

    var bucket = process.env.S3_BUCKET;    
    var key = event.path.replace('/', '');
    
    if (key == '') {
        key = 'index.html';
    }

    // Fetch from S3
    var s3 = new AWS.S3();
    return s3.getObject({Bucket: bucket, Key: key},
       function(err, data) {
            // Handle errors if encountered
            if (err) {
                return err;
            }
            // Determine encoding based on content type (base64 for images, utf8 otherwise)
            var isBase64Encoded = false;
            var encoding = 'utf8';
            
            if (data.ContentType.indexOf('image/') > -1) {
                isBase64Encoded = true;
                encoding = 'base64'
            }
            // Construct the response object with appropriate headers and body
            var resp = {
                statusCode: 200,
                headers: {
                    'Content-Type': data.ContentType,
                },
                body: new Buffer(data.Body).toString(encoding),
                isBase64Encoded: isBase64Encoded
            };
            // Invoke the callback to return the response
            callback(null, resp);
        }
    );
};

```
{{% notice note %}}
This code fetch from S3 bucket and return the static resource to ALB.
{{% /notice %}}

The specific request and response format specify in [This Document](https://docs.aws.amazon.com/Route53/latest/DeveloperGuide/routing-policy-geo.html). Refer to it for more infomation.
5. After create Lambda function, we scroll down to Code tab then paste in the snippet. Save it with `Ctrl+S` (Windows) or File > Save. Then deploy it to our Lambda function.

![3-7](/images/3/Img3_7.png?width=90c)

6. With the snippet deployed, we add the permission for interact with resources in S3 bucket.
    - Choose Configuration tab then:
![3-53](/images/3/Img3_53.png?width=90c)
    - Attach S3 full access policy:
![3-54](/images/3/Img3_54.png?width=90c)
### Add Lamba Function to target group
   Lambda functions can be added to a target group for later use with our Application Load Balancer.

1. Access the AWS Management Console interface:
   - Locate and click on EC2
   - Choose EC2

![3-8](/images/3/Img3_8.png?width=90c)

2. Scroll down and click on the ***Target Group section*** > ***Create target groups***.

![3-9](/images/3/Img3_9.png?width=90c)

3. Choose Lambda function as our target group. Then Click ***Next***:

![3-10](/images/3/Img3_10.png?width=90c)
![3-11](/images/3/Img3_11.png?width=90c)

4. In the next section, add Lamba function to the target group.

![3-12](/images/3/Img3_12.png?width=90c)
Successfully created Target Group:
![3-13](/images/3/Img3_13.png?width=90c)