---
aliases: 
created: 2022-04-24, 7:45:24 pm (Sunday, April 24th)
updated: 2022-04-24, 7:52:15 pm (Sunday, April 24th)
---
Packer includes some functionality to manage saving the state of plugins and rolling back.
- `PackerSnapshot <name>` - takes a snapshot of the current state of your plugins and saves it to `$HOME/.cache/nvim/packer.nvim/<name>`
    - It's basically a table in the format `{ "<plugin-name>": { "commit": "<current-sha-shortened>" } }`
- `PackerSnapshotRollback <name>` - does what you think

## Sources
- https://github.com/wbthomason/packer.nvim/issues/298