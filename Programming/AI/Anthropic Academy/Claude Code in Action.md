## What is Claude Code?
### What is a coding assistant?

Different models use different ways to tackle prompts/tasks

Language models don't necessarily have the ability to do much without external tools to provide context to them

Think of the coding assistant as a liaison between you and the language model

"Tool Use" is the term used for providing instructions to models to enable them to request to use certain tools

Better tool use = can tackle on more complex tasks
Can add tools to Claude Code
Better tool use can also contribute to better security since it means less code is sent to a server for processing

### Tools with Claude

Claude Code has some basic tools out of the box, like reading and writing and searching through files

You can make more tools for Claude to use

### Claude Code In Action

Default tools
Extend tools with MCP
Didn't really get much out of this...

---
## Getting Hands On

### Claude Code Setup


### Adding context

Use `/init` to allow Claude to scan your code and create it's own README (`CLAUDE.md`)

Three types of markdown files Claude uses:
- `CLAUDE.md`: suited for projects and to be shared with other engineers
- `CLAUDE.local.md`: customized for the person using claude; not shared with other engineers
- `~/.claude/CLAUDE.md`: global "config" file

To update the `CLAUDE.md` file through the editor, use `#`. This will merge any instruction you give to `CLAUDE.md`.

Regarding the `@` sign:
- can reference specific files
- if there are multiple files already associated with a specific key term, you can reference all of them with `@`
    - Example: If `CLAUDE.md` has multiple files underneath the section `Architecture > Auth`, all of those files and info can be referenced using `@auth`

### Making Changes

Can paste in screenshots (on Mac, use `Ctrl-V`, not `Cmd-V`)

**Plan mode** is ideal for tasks that need a more thorough understanding of the codebase you're working with

**Thinking modes** are different levels of "reasoning" the model can employ. Essentially, the higher the thinking mode, the more context taken in and the more tokens used.

Here's Anthropic's breakdown on when to use which:

> Planning Mode is best for:
> - Tasks requiring broad understanding of your codebase
> - Multi-step implementations
> - Changes that affect multiple files or components
> Thinking Mode is best for:
> - Complex logic problems
> - Debugging difficult issues
> - Algorithmic challenges

### Controlling Changes

Use `Esc` to interrupt Claude mid response

There's this concept of "memories" where you use `Esc` to interrupt Claude, add a "memory" using the `#` key to tell Claude about a more correct approach, and then continue the convo

Use `Esc` twice to enable "rewinding" conversations
This will allow you to delete irrelevant sections and keep Claude focused

#### Context Management Commands

- `/compact`
    - summarizes current convo
- `/clear`
    - resets the conversation

### Custom Commands

- nav to the `.claude` dir
- create a dir inside of it called `commands`
- create a markdown file with your command name

I think the resulting markdown file is like a set of instruction prompts you would provide Claude

You can add arguments using `$ARGUMENTS`

Here's their example for a `write_tests.md` command:

```
Write comprehensive tests for: $ARGUMENTS

Testing conventions:
* Use Vitests with React Testing Library
* Place test files in a __tests__ directory in the same folder as the source file
* Name test files as [filename].test.ts(x)
* Use @/ prefix for imports

Coverage:
* Test happy paths
* Test edge cases
* Test error states
```

### MCP Servers with Claude Code

Kinda glossed over this one
Talked about the Playwright MCP and using it to generate UI components

### Github Integration

Glossing over this one too since it's talking about using Claude within Github Actions