---
title : "Introduction"
date :  "`r Sys.Date()`" 
weight : 1 
chapter : false
pre : " <b> 1. </b> "
---

#### Introduction

For this workshop, you will use the **Retrieval-Augmented Generation (RAG)** technique to build a generative AI-powered chatbot. A foundation model (FM) in Amazon Bedrock is used to answer your chatbot questions through pre-indexed content. **Amazon Bedrock** is a fully managed service that makes FMs (from Amazon and leading AI startups) available through an API, so you can choose from various FMs to find the model that's best suited to your use case. For storing (indexing) and retrieving relevant content, you use **Amazon Kendra**, a fully managed service that provides intelligent enterprise searches powered by machine learning. You use AWS Lambda as the serverless compute for running the application code in an event-driven manner.

To begin with, in this introduction chapter we will walk through the core concepts for the workshop, Amazon services that support them and the architecture that ties everything together.

![WS2_Architecture](/images/1/WS2_Architecture.svg?featherlight=false&width=70pc "Serve static content through VPC with CloudFront")
#### Contents

- [What is Amazon CloudFront ?](1.1-CloudFront/)
- [Amazon S3](1.2-AmazonS3/)
- [WAF-ALB-Lambda](1.3-WAF-ALB-Lambda/)

In the following sections, we will delve into the fundamental concepts of VPC.
