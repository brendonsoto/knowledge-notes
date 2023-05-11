---
aliases: 
created: 2022-01-06, 11:10:30 am (Thursday, January 6th)
updated: 2022-01-06, 11:16:44 am (Thursday, January 6th)
---
#git

# Merge or Rebase?
When to use one or the other.

Use **merge** when:
- you have pushed your local branch and need to bring in changes from another branch

Use **rebase** when:
- your local branch has *not* been merged and you have to bring in changes from another branch

Why?
Because rebase will re-write the history causing your branch to diverge from origin.

## Sources
- https://stackoverflow.com/questions/19016698/git-branch-diverged-after-rebase
- https://stackoverflow.com/questions/34678950/git-branch-has-diverged-after-rebase-so-why-rebase?lq=1

## Related
- [[Programming/Git/Undo Local Rebase]]