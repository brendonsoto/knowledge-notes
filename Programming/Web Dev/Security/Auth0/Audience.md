---
aliases: 
created: 2022-04-20, 9:35:42 am (Wednesday, April 20th)
updated: 2022-04-20, 9:55:53 am (Wednesday, April 20th)
---

From the [Auth0 glossary](https://auth0.com/docs/glossary):

> The unique identifier of the audience for an issued token, identified within a JSON Web Token as the `aud` claim. The audience value is either the application (`Client ID`) for an ID Token or the API that is being called (`API Identifier`) for an Access Token. At Auth0, the Audience value sent in a request for an Access Token dictates whether that token is returned in an opaque or JWT format.

Alright, so it's basically a way to tell Auth0 "give me an access token for this application/API"