---
tags:
  - web-dev
  - tooling
created: Monday, March 4, 2024 5:18 PM
created_at: 2024-03-04T17:18:08-05:00
---
[Webpack](https://webpack.js.org/) and [Vite](https://vitejs.dev/) are both options for front end tooling. Webpack has been around longer but Vite is gaining popularity. Vite is simpler than Webpack, opting out of a lengthy configuration process like Webpack has, and has a quicker startup time compared to Webpack.

The author of Vite, Evan You, mentioned in a [Hacker News comment](https://news.ycombinator.com/item?id=26972400):
> It is NOT Vite's goal to completely replace webpack. ...
> ...
> Vite is optimized for these common use cases, and we've heard many success stories of painlessly moving from vue-cli/CRA to Vite.

This makes sense considering Webpack's maturity and diverse ecosystem of plugins.

It's also promising hearing other projects using Vite as well. From the same comment:
> ...we are also seeing frameworks like Svelte/Solid/Marko building SSR meta frameworks on top of Vite, projects that were previously webpack-based offering alternative modes running on top of Vite (e.g. Nuxt, Storybook), so we believe Vite does cover quite a lot even for power users.

I just checked some other frameworks, like [NextJS](https://nextjs.org/docs/app/api-reference/next-config-js/webpack) and [NestJS](https://docs.nestjs.com/recipes/hot-reload), and both seem to use Webpack still. Then again, I think Vite came out after these two projects gained momentum.

One thing I was still curious about was how does Vite perform for large codebases? Granted, I have no metrics to define "large", but someone else was able to experiment with this idea through making multiple projects and measuring both build and browser load times ([source](https://betterprogramming.pub/is-vite-really-faster-than-webpack-b414f6cc751c)). Vite starts falling behind Webpack a bit around the 500 files mark, but is able to outperform Webpack once code-splitting and lazy-loading are implemented. The author does include:
> It’s not surprising that browsers aren’t made to efficiently fetch thousands of files in seconds. Because you shouldn’t, really, have 5000 files in one JS bundle.


## When to use one over the other?

It seems like Vite is ideal for the majority of cases and Webpack is ideal for handling niche compilation processes.


## What enables Vite to perform faster than Webpack?

Vite separates dependencies from source code and pre-bundles the dependencies using [esbuild](https://esbuild.github.io/). The source code is served to the browser via ESM. What this means is that a server can make a request for one file and natively import other modules as needed. This helps improve cold-start (the initial bundling and not handling updates) performance since browsers now support ESM. Webpack has to bundle the entire application prior to pushing code to the browser (I guess Webpack by default pushes CJS via web sockets?).

Webpack can handle pushing out changes in source code to the browser via Hot Module Replacement (HMR). HMR works by creating a graph of all of the modules used by the app and mapping out how they're connected. Vite does this too but pushes the changes out via ESM natively, whereas Webpack doesn't seem to. (Could be interesting to explore if that's an option.) Additionally, Vite takes advantage of HTTP headers to improve update performance. If a resource hasn't changed, the dev server returns a [304 Not Modified](https://developer.mozilla.org/en-US/docs/Web/HTTP/Status/304) response to the browser, saving some data transmission. Additionally, some cache settings are set so once a resource is received it will not have to be re-received until it has changed. (It does so by setting `Cache-Control: max-age=31536000,immutable`)


## If ESM is supported and fast, why not use it for production?

The [docs](https://vitejs.dev/guide/why.html#why-bundle-for-production) put it best:

> Even though native ESM is now widely supported, shipping unbundled ESM in production is still inefficient (even with HTTP/2) due to the additional network round trips caused by nested imports. To get the optimal loading performance in production, it is still better to bundle your code with tree-shaking, lazy-loading and common chunk splitting (for better caching).
>
> Ensuring optimal output and behavioral consistency between the dev server and the production build isn't easy. This is why Vite ships with a pre-configured build command that bakes in many performance optimizations out of the box.
