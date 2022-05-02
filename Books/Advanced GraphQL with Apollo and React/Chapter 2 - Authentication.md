---
aliases: 
created: 2022-04-06, 3:11:06 pm (Wednesday, April 6th)
updated: 2022-04-06, 3:53:14 pm (Wednesday, April 6th)
---
A **tenant** in Auth0 is like a container, or an environment.

An **audience** in Auth0 refers to the endpoint
An **issuer** is the Auth0 domain for the endpoint/network.

Tell me this is not confusing to read:

> From there, we can call a set method on request.http.headers and pass in user as the name of the header we want to set, and the JSON-stringified user object from the gateway, or set it to null if it has not been added to the gateway context. After that, we’ll need to retrieve this header from the request once it reaches the accounts service to explicitly set the user context for this service’s ApolloServer:
