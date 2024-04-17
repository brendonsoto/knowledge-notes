---
tags: 
- web-dev
- architecture
- pattern
created: Wednesday, April 10, 2024 8:49 PM
created_at: 2024-04-10T20:49:36-04:00
---
## What is it?

It's like the microservices pattern but for frontend. From the [module federation intro](https://module-federation.io/guide/start/index.html):
> Module Federation is an architectural pattern for the decentralization of JavaScript applications (similar to microservices on the server-side). It allows you to share code and resources among multiple JavaScript applications (or micro-frontends). 

## When is it useful?

The docs mention large applications, microfrontend architecture, and mutli-team development being the use cases. The highlighted feature is separating out code.

## Who made it and why?

The Webpack team created module federation as a way to share code between multiple applications.

More specifically, the [github page](https://github.com/module-federation) mentions Zachary Jackson created it and now it's officially part of Webpack.

## Who uses it?

[A lot of big names](https://github.com/module-federation/module-federation-examples?tab=readme-ov-file#companies-using-module-federation).

## How do you use it?

The gist:
- Create a project that exports something to be used in a different application
- Add the module-federation dependency/ies for your code bundler (e.g. webpack/rspack)
- Update the bundler to export whatever it is you want to export
- Create a project that consumes the exported components from the other application/project
- Add module-federation dependency/ies for that project's code bundler
- Update the bundler to source components from the other project's URL
- Profit

### Example project

The problem module federation solves is sharing code across different applications so we'll need multiple applications. To make things really simple, let's say we're building out two applications that share a component library. As a silly example, we can create an "online shopping suite" where there's an application for buyers and a separate application for sellers. The component library will consist of a button (I know, we're going a little crazy here - watch out Google!).


## What resources are there to learn more?

- There's the [module-federation website](https://module-federation.io)
- A [book from the creator and another person](https://module-federation.myshopify.com/products/practical-module-federation) ($40)

## Questions

### What separates module federation from a monorepo?

The [features section of the guide](https://module-federation.io/guide/start/index.html#-features) lists the following benefits:
> - Code Sharing: Share code, styles, and resources across multiple applications.
> - On-Demand Loading: Load code only when needed, thereby improving performance.
> - Dynamic Updates: Dynamically update code in applications without needing to redeploy the entire app.
> - Support for Multiple Frameworks: Compatible with various frameworks like React, Vue, Angular, etc.
> - Support for Multiple Build Tools: Webpack, Rspack.

This all seems similar to using a monorepo to me. It's like a different approach to the same problem.

I think a big plus is the ability to update code in one module/project/application and see the changes in another without having to reload the other module.

This feels like an alternative to having multiple docker containers whose build step includes processing/building the consumed resource's code.

### Is there something like hot-module reloading?


### How do you tackle state management across applications when using module federation?



### How do you handle cache-busting when using module federation?

I get the idea of not needing to rebuild the entire app, but if caching for static files is being used, which seems to be the norm, isn't that a problem?


### How does module federation play with docker?

I'm thinking in particularly when using docker for development.