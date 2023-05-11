---
aliases: 
created: 2022-01-06, 11:14:37 am (Thursday, January 6th)
updated: 2022-01-06, 11:17:03 am (Thursday, January 6th)
---
#git #how-to

# How to undo a local rebase
- `git reflog`
- look for the commit *before* the rebase
    - note the part that says `HEAD@{<number>}`
- `git reset --hard HEAD@{<number>}`

## Sources
- https://stackoverflow.com/questions/134882/undoing-a-git-rebase

## Related
- [[Programming/Git/Merge or Rebase]]