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
