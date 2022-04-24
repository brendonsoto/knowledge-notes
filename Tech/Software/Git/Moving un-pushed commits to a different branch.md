---
aliases: 
created: 2022-01-14, 8:41:21 am (Friday, January 14th)
updated: 2022-01-14, 8:46:34 am (Friday, January 14th)
---
Scenario:
Consider having the commit history:
`Master -> A -> B -> C`
Commits A, B, and C have been made on top of master but you want them to be on a different branch:
```
Master
  \ -> A -> B -> C
```

Do the following:
- From `master` make a new branch
    - Checkout the new branch and check the history to make sure the changes are there
- On `master`, use `git reset --hard HEAD~X` where `X` is the number of commits back that you want to be a part of different branches
    - in the above example with A/B/C, `git reset --hard HEAD~3`
- Merge the new branch onto `master`

## Sources
- https://stackoverflow.com/questions/2740537/reordering-of-commits
## Related
- [[Tech/Software/Git/Reordering commits]]