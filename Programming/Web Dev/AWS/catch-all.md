---
tags: 
- web-dev
- tools
created: Monday, April 15, 2024 6:09 PM
created_at: 2024-04-15T18:09:38-04:00
---
This is a catch-all for my notes about AWS, mostly for a job application.

What do I need to learn?

- [ ] AWS Serverless architecture
- [x] DynamoDB
- [x] S3
- [x] API Gateway
- [x] Lambda
- [x] Step Functions
- [x] Open Search / Elastic Search
- [x] ECS/EKS
- [ ] networking / InfiniDash / load balancers
- [x] CloudFront

One at a time...

## How AWS Thinks of the Application Stack

AWS breaks down the application stack to three pieces: compute, integration, and data stores.

## Compute

### ECS

Amazon Elastic Container Service (ECS).

I don't get how this is different than kubernetes.

### EKS

Amazon Elastic Kubernetes Service (EKS).

I don't really understand what this is for.



## Integration

### API Gateway

> Amazon API Gateway is a fully managed service that makes it easy to create and publish APIs at any scale.

I guess this is almost like Rails/Django where you can scaffold out an API?

Does this use Lambda under the hood?

Side note: There's an option to make an API *edge-optimized* which helps if geographic distribution is important to you. CloudFront is used to help with the geographic part.

### Step Functions

> AWS Step Functions is a visual workflow orchestrator that makes it easy to sequence multiple AWS services into business-critical applications. 

Sounds a bit like Alloy.

## Data Store

### DynamoDB

> Amazon DynamoDB is as serverless, NoSQL, fully managed database with single-digit millisecond performance at any scale. 

DynamoDB is AWS's NoSQL database.

### S3

> Amazon Simple Storage Service (Amazon S3) is an object storage service designed to store and protect any amount of data.

Data storage.

What separates this from a relational db?


## Network and Content Delivery

### CloudFront

CloudFront is AWS's CDN (Content Delivery Network).

## Other

Idk how to categorize these yet.

### Identity and Access Management (IAM)

This can be used to set up permissions for users and resources (e.g. creating a set of permissions that only allow read access on a database).

### IAM Identity Center

This is for creating accounts for people to use to actually interact with AWS for everyday tasks.

## lol

### InifiniDash

[https://www.theregister.com/2021/07/05/infinidash/](https://www.theregister.com/2021/07/05/infinidash/)



## Setup

See [here](https://aws.amazon.com/getting-started/guides/setup-environment/).


## Questions

How would I set up CI/CD?
I was thinking about this while doing the [build a basic web app tutorial](https://aws.amazon.com/getting-started/hands-on/build-web-app-s3-lambda-api-gateway-dynamodb/module-one/?e=gs2020&p=build-a-web-app-intro). One of the options when starting a new web app via the Amplify console was GitHub. Additionally, when selecting "Deploy without git provider", Amazon S3 is an option next to "Drag and Drop" and "Any URL".


## Brain dump

### I don't understand the aws cli and logging in

I'm trying to follow the [build a basic web app tutorial](https://aws.amazon.com/getting-started/hands-on/build-web-app-s3-lambda-api-gateway-dynamodb/module-one/?e=gs2020&p=build-a-web-app-intro) but am having difficulty uploading the zip file containing the simple `index.html` file to Amplify.

Okay, so AWS credentials carry permissions with them. The permissions are for the different actions you can take on AWS, like downloading a file from S3.

There's the *root user*, also known as the account owner or account root user. This user has access to all AWS services and resources in the account. It is *recommended to not use this account for everyday tasks*. The list of tasks AWS recommends as root-only can be found [here](https://docs.aws.amazon.com/IAM/latest/UserGuide/root-user-tasks.html).

The question then becomes, what do you do then for everyday tasks?

The answer: you create an *IAM Identity Center user*.

An IAM Identity Center user is a user whose account is part of an AWS Organization. These users have a specific URL to use to sign into AWS. When they sign in they are given temporary credentials. It's a [recommended practice to use IAM Identity Center users](https://docs.aws.amazon.com/IAM/latest/UserGuide/id.html#id_sso_users).

You may be asking, what's the alternative?

IAM users. (This you're kind of familiar with from your time at The Bloc) There are differences between IAM users and IAM Identity Center users. The primary ones seem to be IAM users have long-term credentials where the alternative have temporary ones. Additionally, the IAM Identity Center acts as a central hub for all users.

Going back to IAM Identity Center users, you'll need to sign into AWS using the *root user* and create an IAM Identity Center user then. Afterwards you'll create a permissions set and assign it to the created user. Lastly, you'll get a link to sign into AWS that's specific to the account you created. You can follow the instructions for all of this [here](https://docs.aws.amazon.com/SetUp/latest/UserGuide/setup-configadminuser.html).


## What to do if you don't remember the URL for signing into AWS for IAM Identity Center users

- Log into AWS as the root account
- Navigate to IAM Identity Center
- On the Dashboard page, look for *Settings Summary*.
- Look for *AWS access portal URL*