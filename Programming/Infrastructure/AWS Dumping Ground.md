---
aliases: 
tags:
  - aws
  - infra
created: Thursday, November 2, 2023 12:53 PM
created_at: 2023-11-02T12:53:02-04:00
updated: 2023-11-02, 1:02:57 pm (Thursday, November 2nd)
---
Dumping what I've "learned" regarding AWS here.

I don't really know much in this area and haven't thought to dedicate too much time to it since it's so specific to AWS.

## Auth / SSO

You know of logging in via the CLI through `aws sso login`. That adds some files in `~/.aws/sso/cache/*.json`. One of these files an access token that can be used in other commands like `aws sso get-role-credentials --access-token <token> ...`.

Here's a [github issue thread](https://github.com/aws/aws-cli/issues/5261) on AWS not responding to people wanting a cleaner way of getting the access token (like using the `aws` tool instead of manually grabbing it from the file).