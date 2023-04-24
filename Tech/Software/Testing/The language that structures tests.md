---
aliases: 
tags: testing language
created: Monday, April 24, 2023 11:15 AM
created_at: 2023-04-24T11:15:28-04:00
updated: 2023-04-24, 11:16:34 am (Monday, April 24th)
---
I'm going to use the following for a bit:
```
// utils.test.ts
// Let's imagine I'm testing a module named 'utils' that's used for a pair of nav buttons
// It exports an object w/ 2 props: next & prev.
// Both have their own properties: isDisabled & onClick


// Notice the lack of an over-arching `describe('utils'...)` statement
// Also notice the colon. This is to quickly find sections if a test readout
// merges all nested describe blocks.
describe('next.isDisabled:', () => {
    // ...
})

describe('next.onClick:', () => {    // Get rid of nesting
  describe('triggers a modal to open when:', () => {  // Results oriented
    //...
  })

  describe('switches to the next page when:', () => {
        //...
  })
})
```