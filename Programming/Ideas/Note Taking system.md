## General

- Tag everything
- If not tagged, auto goes to untagged where a timer is set to delete the note if not tagged by the timer's end

## Index / Home screen

### idea 1: tags
- shows just tags
- almost like bitwig menu
- selecting one group of tags opens up a second menu to the right of it where the top item is *just \<tag\>* and the items/rows underneqth are other tags that appear along the selected tag

### idea 2: fzf-like trie

- fzf/telescope/ google-like search bar
- as you type, sentences appear that form options
    - imagine you have the files `how-to-tie-knot.md` and `how-to-whistle.md`. You are greeted witb the prompt and atart typing "how to". The results will show you the two results

## new idea
I wonder if there are natural groups that arise.
I was thinking of having a *How do I* folder where some command or prompt including "how do i" would search those files.
If an entry doesnt exist, you can continue typing the question, hit enter, and a new file will be created.
The file will have some front-matter/metadata already included like when the file was created, a "how-to" tag, and a header.
Perhaps this can be a temp file...if nothing is written below the header, the file can be considered empty and deleted.
Additionally, spell check would be nice...

Generally, I have "how-to" files and sometimes notes from things I read.
I usually don't look back at my notes, unless if it's for work stuff.
This leads me to another categroy of notes: "what is/are" notes!
This is more like a **glossary**...

For work, I usually like to have notes for tickets Im working on.
That could be nice to have by the ticket ID and name.
Maybe a little TUI pops up that asks for the ticket ID and the ticket name.
There can be a config element to select what ticketing system js being used and to auto-prepend the ticketing prefix (e.g. `SC-` for shortcut).

Im wondering about each of these being its *own directory or tool* and then having *another tool to join them.*

So I would have a:
- how-to tool
- glossary tool
- ticketing/braindump tool

And since each can have their own CLI tool they can be accessed by either the tool's own name or through the joining tool.

Id want all of this to be accessible from neovim so this would probably be a telescope plugin.
Unless...
Have a config file that exports paths to the dirs as env vars.
Another config option could be editor, or just use `$EDITOR` .
Then any flags to pass in for opening the tool (e.g. opening nvim with `:Telescope fd`)
