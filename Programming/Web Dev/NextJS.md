---
tags: 
- web-dev
- javascript
- framework
- front-end
created: Tuesday, March 5, 2024 2:10 PM
created_at: 2024-03-05T14:10:17-05:00
---
[NextJS](https://nextjs.org/) describes itself as "The React Framework for the Web". It looks like an opinionated approach to build web applications. The [introduction docs](https://nextjs.org/docs)state: "Next.js is a React framework for building full-stack web applications."

Ahh, the introduction part definitely gets more to the point of what NextJS takes care for you:
- Routing
- Rendering (Client and server-side)
- Data fetching (with memoization, caching, and revalidation)
- Styling (CSS Modules, Tailwind, CSS-in-JS)
- Optimizations (assets and scripts)
- TypeScript

## Why was it built?



## Learning NextJS

They have a [course](https://nextjs.org/learn). I'll go through the course first and then the docs to check for any differences.

The course seems like it's more to drive NextJS's main features. Quote from chapter 1:

> Unlike tutorials that have you write code from scratch, much of the code for this course is already written for you. This better reflects real-world development, where you'll likely be working with existing codebases.
>
> Our goal is to help you focus on learning the main features of Next.js, without having to write _all_ the application code.

### Chapter 1: Getting Started

Interesting. `/app/lib` holds shared functionality. The language makes it seem like any shared functionality is hoisted up the file tree, but I guess this will be confirmed going through the course more. I'm weirdly excited to try this approach out since I've been thinking on and off on how to best share functionality across a codebase without overwhelming devs.

They also use `/app/ui` for shared components. This isn't a big deal or anything; I'm used to seeing something like `/app/components` so I figured I'd make a note.

Regarding typing out data models, they recommend Prisma.

### Chapter 2: CSS Styling

For styling, they use Tailwind. CSS Modules are also supported. It's not that other solutions (e.g. styled-components) aren't available. NextJS doesn't seem to ship with those out of the box.

They also recommend [clsx](https://www.npmjs.com/package/clsx) for conditionally applying classes. I think the syntax is a bit funky (e.g. having the style first instead of the condition).

**NOTE:** I saw a `prettier` config in the app files. I wonder if there are any git hooks automatically set up to run prettier before commit.

### Chapter 3: Optimizing Fonts and Images

NextJS downloads any font files at build time and hosts them with your other static assets. This is to prevent another network request on the user's side.

I don't totally understand this optimization. If the fonts weren't hosted on the same server as the other files, wouldn't the client still have to make a network request for the font files? Additionally, some font services may be faster than the server used to distribute the web app. Consider Google fonts. Google probably has a way faster content delivery system than the majority of other tech companies.

Images are also optimized, but by using a NextJS component called `Image`. I'm not super sure how NextJS performs the optimizations but the docs mention it optimizes by:
-  "Preventing layout shift automatically when images are loading."
- "Resizing images to avoid shipping large images to devices with a smaller viewport."
    - This is the one I really don't get. The component has `width` and `height` props. Are they treated as `max-*` values? There's also a `src` prop to define which image to use. It's not like it takes a string and searches a directory to swap out assets depending on other props/variables.
- Lazy loading images by default (images load as they enter the viewport).
    - This is nice.
- Serving images in modern formats, like WebP and AVIF, when the browser supports it.
    - Are people actually using these formats? It still seems like PNGs and SVGs are the de facto.

### Chapter 4: Creating Layouts and Pages

NextJS uses something called file-system routing (not sure if that's an widely used term) for creating pages. All pages live within the `/app` directory.

To create a page:
- create a subdirectory within `/app` (or under `/app/other-route` if the new page belongs to another page)
- add a `page.tsx` file within the new subdirectory

To add a shared layout, a `layout.tsx` file can be added as a sibling file to `page.tsx`. The component can render whatever but must also have a spot for the `children` prop (makes sense).

This is an interesting take on file structure. It features the philosophy of "keeping shared things together" but in a different way than I'm used to. I'm used to having a `/layouts` directory near the root of the application. This approach makes not only sharing layouts between pages easy but also acts as a quick reference point for other developers to see what layouts are available. I found that last point helpful for applications spanning multiple pages where the pages are split between different teams and the teams don't really communicate with each other (leading to rebuilding the same stuff). That's not to say I don't like this approach; I do. I'm thinking as an application and team expand, would this approach still hold? I guess one way to resolve this is to use a combo of the approaches. There can still be the `/app/**/*/layout.tsx` files and those files could share layouts and/or components from `/app/ui`.

Another nice thing I'm learning through this: it's okay to have components with the same name. I'm not just talking file name; every `page.tsx` file exports a component named `Page`. I do wonder though, wait, will add as a question.

#### Questions

##### How does NextJS know to look for page.tsx? Where's the magic?!

Was peaking around the source code, but couldn't find anything definitive just yet...

##### If every page exports a `Page` component, how does the React DOM tree look like in the React dev tools? Is it hard to identify nested pages?

Hmmm, looking at the React dev tools for the nested invoices page there's no `Page` element to be found at all.

Ahh, I think I found it through the dev tools. There are context providers called `TemplateContext.Provider`. These providers have a `key` prop whose values can be put together to form the route of the page. There is one of these context providers whose key is not part of the route but instead is `__PAGE__`. I am guessing this provider represent the `Page` component.

I'd have to go through the source to confirm. That sounds fun.

### Chapter 5: Navigating between pages

NextJS has a `Link` component exported from `next/link` (default export). It looks, prop-wise, very similar to an `<a>` tag. Adding it enables the app to *feel* like a SPA (Single Page Application).

I learned NextJS defaults to server-side rendering React. The `Link` component triggers the scripts/content for the related page to be prefetched once the component enters the viewport.

Speaking of server-side rendering, another interesting thing I learned is hooks can only be used on the client side, at least within the context of NextJS.

#### Questions

##### If page content/scripts are prefetched when the Link component is in view, how come I don't see network requests for the 'customers' and 'invoices' pages on page load?


## Caveats / Good to know

- There are two different routers:
    - app router -- the newer router; enables using React's latest features (e.g. Server Components and Streaming)
    - pages router -- the original router; can be used for server-side rendering
        - The language in the docs imply the pages router is for legacy NextJS applications