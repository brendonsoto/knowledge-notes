---
aliases: 
created: 2022-08-19, 1:29:39 pm (Friday, August 19th)
updated: 2022-08-19, 1:29:59 pm (Friday, August 19th)
---
I keep repeating this so documenting in one place to further refine:

## Side notes

I may use *directory* and *folder* interchangeably. Let me know if that’s bothersome and I’ll change the lang to use just one (probably “folder” since that seems more like how most people talk about it).

Ditto with *utils* and *helpers*. My brain always associates seeing *helpers* with a back-end file structure where there are these umbrella categories.

I also talk about *presentational components*. Some people know these as “dumb” components. The gist is a presentational component is more focused on visuals and doesn’t have much logic behind it. For more, check out this [Medium article by Dan Abramov](https://medium.com/@dan_abramov/smart-and-dumb-components-7ca2f9a7c7d0) (creator of Redux) and this [article from Patterns.dev](https://www.patterns.dev/posts/presentational-container-pattern/).

## Problem

There is no clear organization to the file structure behind Daffy’s front end. This is confusing for new engineers trying to understand the codebase since there’s no clear pattern to go off of. The lack of structure inhibits creating a clear standard and promotes multiple ways of doing the same thing. An engineer should spend the least amount of time possible trying to understand where things are within a codebase.

Below are screenshots of the current state in both Visual Studio Code and on the command line.

![Screen Shot 2022-08-19 at 12.01.22.png](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/2c2eacbe-be15-45e5-81db-e511a6cfd8d0/Screen_Shot_2022-08-19_at_12.01.22.png)

![Screen Shot 2022-08-19 at 12.00.08.png](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/a9448333-2995-41e2-acdc-162282bb79b6/Screen_Shot_2022-08-19_at_12.00.08.png)

## Proposed Structure

Here’s a generic template:

```
src/
- components/ # Any components that are used in multiple places
- layouts/    # Any templates
- pages/      #
- store/      # Any logic related to state management (e.g. Redux)
- utils/      # aka Helpers, but used in multiple plaes
- types/      # Any *.t.ds files for third-party or globally used types
- app.tsx     # The root node/component that ties everything together.
- styles.ts   # Global styles. This example uses styled components but can be CSS or anything else.
```

The idea behind this is to **group code by feature** not by its role (e.g. “all the helpers go in the `helpers` directory and all of the styles in the `styles` directory…).

Let’s take a moment to check out these in more depth.

### What does “multiple places” mean?

“multiple places” refers to separate directories. For example, imagine you have an app with `Login` and `Logout` pages, both using a `Button` component. This scenario would have the following directory structure:

```
src/
- components/
  - button
- pages/
  - login/Login.tsx    # Uses components/button
	- logout/Logout.tsx  # Uses components/button
```

### What does the `components` directory look like inside?

There are different approaches to this. The approach I recommend is making a directory per component. That way code can be grouped by function rather than type. For example, let’s imagine we have a header section that takes up the full width of the page and has a toggle for dark mode. Here’s what the files for that component may look like:

```
src/
- components/
  - header/
    - index.tsx
    - Header.tsx
    - Header.test.tsx
    - utils.ts
    - utils.test.ts
    - styles.ts
    - types.ts
```

The first thing you might be thinking is “why an `index.tsx` file?”. The idea is to have an `index` file as an interface for exporting anything relevant to this file. This includes the main component and may include other things like types.

Another approach is to omit `Header.tsx` and use `index.tsx` as the file holding the component. This works fine if you’re not exporting anything outside of the component.

If a component has other components within it and those sub components are **not** used in other components, a directory named `components` may be included within the same directory. Using the above example, let’s say the header has a login section that triggers a login pop-up. The directory would then look like:

```
src/
- components/
  - header/
    - index.tsx      # The main component
    - components/    # Sub components that are needed to make <Header>
      - loginCTA/    # The pattern continues...
        - index.tsx  # The login component
        ...          # Any other files related to the login component
```

### Can you explain in more detail what a “layout” is?

The intent behind the `layouts` folder is to hold any presentational components whose purpose is to align other components. Think of how most websites have a navbar section, maybe a side bar, a main content area, and a footer. For examples, check out this [MDN article](https://www.patterns.dev/posts/presentational-container-pattern/) or this [article from Adobe XD](https://xd.adobe.com/ideas/principles/web-design/11-website-layouts-that-made-content-shine-in-2019/).

## A bit more info on `pages`...

The `pages` directory holds components that may bring together elements from the other directories (`components`, `layouts`, `store`, `utils`). The idea is that each page is it’s own directory. If there are components related to just that page, there may be a `components` directory within the page directory. This is the same concepts as in the section [What does the `components` directory look like inside?](https://www.notion.so/Proposal-for-Daffy-Front-End-File-Structure-464411a083344fafa7dfb5d5f2013ce2). As an example, let’s imagine we have a login page that has a form. This form is used *only in the login page*, no where else. Here’s what that may look like:

```
src/
- pages/
  - login/
    - index.tsx      # The Login page
    - components/    # Components only used in the Login screen
      - loginForm/   # One of the components
        - index.tsx  # The same pattern as any other components...
        - ...        # Any other loginForm relevant files
```

## What’s the deal with `store`?

The `store` directory is for any logic specific to your app’s state management *on a global level*. Think any state that can be manipulated in multiple components (e.g. filters) or data that’s shared between pages. The name “store” is kept general so it’s not tied to any specific state-management tool (redux, mobx, xstate, etc.).

Regarding the files within `store`, the structure is similar to `components` and `pages`: a nested structure that repeats a pattern. Often the state of an app is represented like a tree. Each node of that state tree has its own directory and can hold other nodes.

For a more concrete example, here’s a structure for an app that uses [redux and slices](https://redux.js.org/tutorials/essentials/part-2-app-structure):

```
src/
- store/
  - index.ts
  - slices/
    - evaluations/
      - index.ts                   # Exports the state slice and any types
      - evaluationSlice.ts         # The slice itself
      - evalutationsSlice.test.ts  # Yay testing!
      - utils.ts                   # Helpers
      - utils.test.ts              # Yay more testing!
      - types.ts                   # Optional. Maybe types are just in the slice file.
```

If wondering “why does the index file export types too? why not just import straight from the types file?”, the idea is for the index file to be the interface to everything related to this piece of state.

If a piece of state needs to be broken down into multiple pieces/slices the same pattern as the other root-level directories can be taken: nested slices.

## Common questions regarding this approach

### Why have a `components` directory when we have a component library?

One idea behind having a separate `components` directory for commonly used components is to use that local directory to discover what can be moved into a common library.

### Why not put all of the components into the root level `components` directory instead of having sub `components` directories? Wouldn’t that make discoverability harder?

Yes, discoverability of existing components can be an issue here. I’m currently unaware of a guard against this. On the flip side, having all components within a single directory can also negatively impact discoverability as a developer may open the directory to see an entire list of components! You can group the components then by function or page, but at that point is it much different than having a nested directory?

### Where are tests? Why isn’t there a `tests` folder?

Tests live next to the file/module to be tested. Keep related code together.

There could be an `e2e` or `e2e-tests` folder for more global integrated testing.

### Why should I believe you that this is a sound structure?

I picked this structure up from my time at the NHL. All of the apps were built this way. While there I rebuilt the UI for their Stats web-app and implemented this pattern. During my last two weeks I was able to transfer the application and knowledge of the app’s hairy bits to a new engineer within a week. The next week they were picking up where I left off, making modifications across multiple directories.

Since then I’ve seen and advocated for this pattern at other places I’ve worked at. So far it has been received positively although I don’t have any data to point to.

I’m sure there are plenty of other blog articles about “how to structure your web-app” for other ideas.