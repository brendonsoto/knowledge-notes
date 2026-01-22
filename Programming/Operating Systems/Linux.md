---
created_at: 2026-01-21T23:19:00Z
---

# Linux

## Problems and Solutions

### Headphones are not working

Are you using pipewire?
To check, try running `pipewire --version`
If so, run:
- `systemctl --user restart pipewire.socket`
- `systemctl --user --now enable pipewire`

[Solution source](https://www.reddit.com/r/pop_os/comments/v3g2w9/is_there_a_cli_command_to_restart_pipewire/)

For more on audio:
- [Old but useful info on linux audio stack](https://venam.net/blog/unix/2021/02/07/audio-stack.html)
- [Useful Github readme on pro audio on linux](https://github.com/scottericpetersen/pro-audio-on-linux?tab=readme-ov-file)
