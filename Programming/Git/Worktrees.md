# Git Worktrees

## File structure
[kudos](https://morgan.cugerone.com/blog/how-to-use-git-worktree-and-in-a-clean-way/)
[and this too](https://morgan.cugerone.com/blog/workarounds-to-git-worktree-using-bare-repository-and-cannot-fetch-remote-branches/)

Gist:
- setup dir: `mkdir <my-project-path> && cd <my-project-path>`
- clone bare repo: `git clone --bare <repo> .bare`
- set up a `.git` file with: `gitdir: ./.bare`
- add to `.bare/config`:
```
[remote "origin"]
  url = git@github.com:UseAlloy/Alloy.git
  fetch = +refs/heads/*:refs/remotes/origin/*
```
- test with `git status`
