---
aliases: 
created: 2022-02-09, 4:08:39 pm (Wednesday, February 9th)
updated: 2022-02-09, 4:10:13 pm (Wednesday, February 9th)
---
**Problem:**
`fatal: ref refs/remotes/origin/HEAD is not a symbolic ref`

**Solution:**
`git symbolic-ref refs/remotes/origin/HEAD refs/remotes/origin/main`

*Why does it work?*
You're setting up the symbolic ref

## Sources
- https://stackoverflow.com/questions/45811971/warning-ignoring-broken-ref-refs-remotes-origin-head