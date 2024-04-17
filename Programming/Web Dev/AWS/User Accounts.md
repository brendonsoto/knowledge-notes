---
tags: 
- web-dev
- aws
created: Tuesday, April 16, 2024 4:27 PM
created_at: 2024-04-16T16:27:12-04:00
---
## The different types of user accounts

AWS credentials carry permissions with them. The permissions are for the different actions you can take on AWS, like downloading a file from S3.

There's the *root user*, also known as the account owner or account root user. This user has access to all AWS services and resources in the account. It is *recommended to not use this account for everyday tasks*. The list of tasks AWS recommends as root-only can be found [here](https://docs.aws.amazon.com/IAM/latest/UserGuide/root-user-tasks.html).

The question then becomes, what do you do then for everyday tasks?

The answer: you create an *IAM Identity Center user*.

An IAM Identity Center user is a user whose account is part of an AWS Organization. These users have a specific URL to use to sign into AWS. When they sign in they are given temporary credentials. It's a [recommended practice to use IAM Identity Center users](https://docs.aws.amazon.com/IAM/latest/UserGuide/id.html#id_sso_users).

You may be asking, what's the alternative?

IAM users. (This you're kind of familiar with from your time at The Bloc) There are differences between IAM users and IAM Identity Center users. The primary ones seem to be IAM users have long-term credentials where the alternative have temporary ones. Additionally, the IAM Identity Center acts as a central hub for all users.

Going back to IAM Identity Center users, you'll need to sign into AWS using the *root user* and create an IAM Identity Center user then. Afterwards you'll create a permissions set and assign it to the created user. Lastly, you'll get a link to sign into AWS that's specific to the account you created. You can follow the instructions for all of this [here](https://docs.aws.amazon.com/SetUp/latest/UserGuide/setup-configadminuser.html).

## Problems and solutions

### What to do if you don't remember the URL for signing into AWS for IAM Identity Center users

- Log into AWS as the root account
- Navigate to IAM Identity Center
- On the Dashboard page, look for *Settings Summary*.
- Look for *AWS access portal URL*