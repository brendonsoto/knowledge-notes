---
tags: 
- aws
created: Wednesday, April 17, 2024 4:23 PM
created_at: 2024-04-17T16:23:02-04:00
---
> AWS Lambda is an event-driven, pay-as-you-go compute service that lets you run code without provisioning or managing servers. 

AWS Lambda allows you to run code without needing to create a server.


## Layers

Layers -- how you can add external functionality, like libraries, to your application. The extra code needs to be packaged as either a zip file or as a container image with all of the dependencies included in the image.

## Questions

### How can a Lambda function connect to other services, like a database?

### How can I use a container image as a Lambda function?

It looks like [Amazon Elastic Container Registry (Amazon ECR)](https://aws.amazon.com/ecr/) is the answer.

### How is version control handled in the context of Lambda functions?

### What do you do if you need to access a secret? Like DB credentials?

The "Security" part of the [Serverless Multi-Tier Architecture paper](https://d0.awsstatic.com/whitepapers/AWS_Serverless_Multi-Tier_Architectures.pdf) mentions using either AWS Key Management Service (KMS) with environmental variables or AWS Secrets Manager.