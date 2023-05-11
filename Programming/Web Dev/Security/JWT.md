---
aliases: "json web token"
created: 2022-04-06, 3:12:43 pm (Wednesday, April 6th)
updated: 2022-04-21, 10:24:56 am (Thursday, April 21st)
---
JWT = JSON Web Token

A JSON Web Token is a type of **access token**.
Access tokens allow clients to make requests to an API on behalf of some user.

There are *three parts* to a JWT:
- header: details about the token type and what algorithm was used to "sign" the token (like an object)
- payload: I think this is just dat (like an object)
- signature: data that helps to confirm the data was not tampered with

Each part is encoded via *Base64* and then concatenated together.

Do *not* put any **sensitive information** in the JWT.
It's only Base64 encoded so it can be easily decoded.

## Resources
Helpful decoder:
https://jwt.io/

