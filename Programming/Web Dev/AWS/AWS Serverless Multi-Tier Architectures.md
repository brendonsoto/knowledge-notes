---
tags: 
- aws
- paper
created: Wednesday, April 17, 2024 3:58 PM
created_at: 2024-04-17T15:58:56-04:00
---
# AWS Serverless Multi-Tier Architectures
With Amazon API Gateway and AWS Lambda

First Published November 2015
Updated October 20, 2021

[link](https://d0.awsstatic.com/whitepapers/AWS_Serverless_Multi-Tier_Architectures.pdf)

---

## Simply summary

Amazon shows how using AWS API Gateway and Lambda can simplify web application development. The simplification comes from reducing some of the boilerplate involved with creating web applications such as server/OS management, writing code to enable communication between different layers (like a message queue), API setup, security, scalability, and more.

All of this is discussed in the context of a three-tier architecture consisting of a presentational tier (UI), logic tier (API), and data storage tier (databases).

## On Lambda

Lambda can also be useful in event-driven applications. Two examples the paper gives are processing files in S3 and streaming data records from Amazon Kinesis (a service for processing video and data streams in real-time).

Lambda functions can exist as either zip files uploaded to S3 or as a container image with all of the needed dependencies.

## API Gateway with Lambda functions

Lambda combined with API Gateway form a typical API. The API Gateway acts as the frontend to the Lambda.

API Gateway and Lambda functions can connect to each other via proxy or non-proxy integrations. The proxy integration sends the entire request as an `event` parameter to the Lambda function. This seems to be the default configuration. The non-proxy integration allows configuring the parameters, headers, and body of the request and what the response looks like to greater detail.

It's possible to configure the API Gateway to use a variable to point to different versions of a Lambda function. Think about the implications of this. If you had multiple environments you wouldn't need to create X versions of API Gateway for X environments. You can create one and use a stage variable to point to different Lambda functions.

## API Gateway performance

API Gateway sits on top of Amazon CloudFront distribution to allow for better regional access of the API using "edge locations". This can also help prevent DDoS (Distributed Denial of Service) attacks.

There's also an option to have API Gateway use an in-memory cache for responses. This helps reduce the number of times a Lambda function is called.

## API Gateway integrations

Logging can be added using Amazon CloudWatch.

Debugging can be added using tracing from AWS X-Ray.

Not really an integration but there's a thing called a canary release where you can release a new version of an API to a subset of your total audience. It's kind of like A/B testing.

## Security

Lambda functions have an *execution role* which is a set of permissions set in IAM (Identity and Access Management). The execution role also dictates what other AWS resources the lambda function can interact with, like DynamoDB.

Since Lambda functions can interact with both other internet endpoints and your data tier it's important to take measures to isolate the data tier, like using a subnet.

## AWS Serverless Application Model (SAM)

[AWS Serverless Application Model](https://aws.amazon.com/serverless/sam/) is a framework for managing Lambda functions. It includes a template syntax for describing functions and their configurations alongside a CLI for local development and debugging.

This is an alternative to using AWS CDK, a framework for describing infrastructure and provisioning through CloudFormation via programming languages. The paper describes AWS CDK as the imperative approach and AWS SAM as the declarative approach.