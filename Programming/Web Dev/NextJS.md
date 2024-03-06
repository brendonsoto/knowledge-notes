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

## Caveats / Good to know

- There are two different routers:
    - app router -- the newer router; enables using React's latest features (e.g. Server Components and Streaming)
    - pages router -- the original router; can be used for server-side rendering
        - The language in the docs imply the pages router is for legacy NextJS applications