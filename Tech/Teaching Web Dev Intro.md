---
aliases: 
created: 2021-12-28, 7:53:31 pm (Tuesday, December 28th)
updated: 2022-01-03, 8:19:38 pm (Monday, January 3rd)
---
We can explore concepts through building a site iteratively. One thought that comes to me is a music site. There can be a home page with static content, a page to show songs and add to a "cart", a page to add a song through a form, and a "checkout" page. Song here will just be the metadata for a song, not the actual audio itself. We'll end up rebuilding pieces of it to explore different approaches.

## Overview
We'll build a four page site about music.
The first page will be the home page with just static content: lorem ipsum and images.
The second page will be a "catalog" of songs.
You can add songs to your cart to buy.
A song here will just be metadata, not the actual audio.
The third page will be a checkout page to "buy" whatever songs you made.
The last page will be a form to upload your own "songs".

## Audience
I'm going to assume super basics of web development skills meaning:
- HTML:
    - Can make a shell page (empty page w/ no content but w/ head & body tags)
    - knowledge of divs
- CSS:
    - knowledge of margins + padding
- JS:
    - knowledge of variables (not specifically between var/let/const, but just saving a value to some variable)
    - function (don't care if arrow vs `function` keyword; will end up teaching both)

I'm going to keep it there for now. Super low flooring.

## What should somebody come away from this experience with?
For HTML:
- basic knowledge of semantic markup:
    - `main` tag for content
    - `section` tag in place of `div` tags for sections of contextual content
    - use `div` tags for positioning/layout
    - `nav` tag
    - how to correctly use `h1` - `h6` tags
        - as a side, how `header > h1` is not valid

For CSS:
- `flexbox`
    - how to make multi-column layouts w/ flexbox
- `grid`
- when to use `flexbox` or `grid`
- CSS animations?
- percentages vs exact pixels for dimensions

For JS:
- `var` vs `let` vs `const`
- scope
- `function` vs arrow functions
- JSON
- ESLint
- prettier
- closures
- `create-react-app`
- React Router
- gauging npm packages
- unit testing
- integration testing?
- e2e testing
- NodeJS
    - expressjs
    - nestjs?

For DB:
- relational dbs w/ (sqlite vs MySQL vs Postgres?)
    - setup
    - creating dbs
    - creating tables
    - putting data in
    - getting data out
    - basic joins (no left or right or etc. just basic `join ... on`)

Other:
- MOBILE FIRST DEVELOPMENT
- how to use dev tools
- MDN / Other reputable sources of info
- cross browser testing



## What's not being covered and why?
- authentication
    - i'm lazy/don't want to cover it
    - i don't know terribly much about it
    - third party resources/tools (i.e. Auth0, passport, etc)
- server-side rendering
    - I don't think it's really necessary coming out of the gate as a junior?
    - could be an exercise
- front-end/client-side performance
    - don't want juniors thinking about performance _just_ yet. trying to prevent preemptive optimizations

## Design
### Shared
#### Navbar
Mobile:
- hamburger menu
- links displayed in a column

Desktop:
- links to the left in a row
- Some other info on the right

#### Footer
- content centered
- two columns
    - left has "About us blurb"
    - right has copyright whatever
    - stacked on mobile

### Home page
- splash image
- text on top
- three sections below
    - each section is two cols in a 2:1 ratio
    - the bigger column has an image
    - smaller column has lorem ipsum

## Lessons / Sections
### 0: Idk
- make sure they know _why_ tools like React exist
    - if not, make a brochure site / scaffold out multiple pages w/ a nav bar
- git

### 1: The home page
#### Goals
HTML:
- `nav`
- `main`
- `h1-6`
- `footer`

CSS:
- `flexbox`

JS:
- know about `create-react-app`
- React Router
    - pages
    - links
    - history

#### Path to the goals
- Start off w/ whatever `create-react-app` provides
- _commit_
- _make new branch_
- Swap default content w/ goofy content
- _commit_
- Add a header to the home page
- _commit_
- make 3 other pages
- _commit_
- add headers to those too
    - Use this to see if they pick up on the idea of components intuitively or not
- _commit_
-

---

## Notes from actual meets
### Start of 2 after 1
Things to review:
- flexbox
- absolute positioning

## Taking an alternative approach
Let me think of this in terms of capabilities.
What's a simple full feature project that's releasable?
A blog/bio page?
Let me role back the releasable part for now.

I think a nice progression would be
- simple static site/s based off of existing sites (no functionality)
- a multi-page web site (no func)
- React / templates
- forms
- servers
- database
- using javascript for live interactions (e.g. updating cost on adding/removing items, menu bar navigations, accordions?)

Im thinking every week make a site in addition to the bigger project.
Maybe end up building a comic selling and uploading site.

Was looking at Marvel, DC, Image, and Comixology sites.
Cross out Comixology because its basically Amazon.
The rest of them are pretty similar.
- mobile view has header with:
    - ham burger menu
    - title or logo in middle
    - search bar
- some carousel at the top
- highlighted content
- news-ish area like the NYTimes
- footer
- comics page

The *biggest* takeaways are being able to:
- Render static (hard-coded) content
- Fetch data
- Render dynamic content
- Communicate errors
- Send data
- Make a simple server that can read and write to a database

I'm thinking of structuring it:
- make the home page but leave out the news part
    - start with github.io page as "prod"
    - practicing base HTML and CSS skills
    - introduce React and the idea of components to rebuild stuff in React
    - reinforce thinking of releases with features/content to think of the "why" behind work
- introduce fetching via the news section
    - light intro to fetch and JSON
        - make json data file
        - try fetching it to show you need a server
        - use simple python command to spin up a server for the files
    - using for loops in React to render multiple similar things
- make the comics section
    - intro to react router
    - make new page
    - make comics.json
    - render comics
        - intro to grid
- make the checkout section
    - no server (idea is to use in memory/state for now)
    - make a form for payment details
    - validation
- make a page to show "My Comics"
    - make data structure  include the comics and whether they're  purchased or not
- introduce the idea of "users"
    - use local state for now
    - login page
    - log out
- introduce db
    - start by pointing out when you restart the server or the site, data is lost
    - basic users table
        - simple hashing for now
    - basic news table
    - basic comics table
    - table for comics to users
    - fetching from the server instead