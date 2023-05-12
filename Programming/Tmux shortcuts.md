---
tags: tmux shell
created: Thursday, May 11, 2023 9:18 PM
created_at: 2023-05-11T21:18:46-04:00
---

These aren't the same as what you'll find when using `<C-?>`. These are what I wish were shortcuts.

**NOTE:** My prefix is `<c-a>`

## Changing the directory of the current session
- `<prefi> :` -- open the prompt
- `attach-session -t . -c /path/to/dir`
    - `-t` = target session
        - `.` = current session
    - `-c` = working directory