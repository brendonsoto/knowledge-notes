---
aliases: 
created: 2022-07-20, 4:18:23 pm (Wednesday, July 20th)
updated: 2022-07-20, 4:21:54 pm (Wednesday, July 20th)
---
WIP

*What made you curious about this?*
Seeing a bunch of `useCallback` hooks with `state`/objects in the `deps` arg.

There are several types of `Dispatcher` objects.
**TODO:** Figure out what they are for/how they're used.

I looked at once, `HooksDispatcherOnMountInDEV`, and used that as a path to go down.

Here's the call stack I found:
- [useCallback](https://github.com/facebook/react/blob/3ddbedd0520a9738d8c3c7ce0268542e02f9738a/packages/react-reconciler/src/ReactFiberHooks.new.js#L2534)
- [updateCallback](https://github.com/facebook/react/blob/3ddbedd0520a9738d8c3c7ce0268542e02f9738a/packages/react-reconciler/src/ReactFiberHooks.new.js#L1876)
- [areHookInputsEqual](https://github.com/facebook/react/blob/3ddbedd0520a9738d8c3c7ce0268542e02f9738a/packages/react-reconciler/src/ReactFiberHooks.new.js#L326)
- [is](https://github.com/facebook/react/blob/3ddbedd0520a9738d8c3c7ce0268542e02f9738a/packages/shared/objectIs.js#L14)

This has been interesting.