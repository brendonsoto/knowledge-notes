---
aliases: 
tags: mac terminal cli
created: Monday, May 22, 2023 9:32 PM
created_at: 2023-05-22T21:32:55-04:00
updated: 2023-05-22, 9:35:44 pm (Monday, May 22nd)
---
**Problem:**
Your terminal is slow.
Opening a new window (via tmux) is slow or just the time from hitting enter on an empty line to a new prompt.

**Solution:**
Removing Apple System Logs (asl):
`sudo rm /private/var/log/asl/*.asl`

**Sources:**
- [OSXDaily](https://osxdaily.com/2010/05/06/speed-up-a-slow-terminal-by-clearing-log-files/)
- [Devroom.io](https://www.devroom.io/2011/11/08/fixing-a-slow-starting-terminal-or-iterm2-on-mac-os-x/)
- [Super User](https://superuser.com/questions/444614/how-to-check-what-slows-down-my-terminal-startup)