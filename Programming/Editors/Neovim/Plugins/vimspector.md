---
aliases: 
created: 2022-05-10, 6:58:22 pm (Tuesday, May 10th)
updated: 2022-05-10, 7:09:01 pm (Tuesday, May 10th)
---
[github.io page](https://puremourning.github.io/vimspector-web/)
[github repo](https://github.com/puremourning/vimspector)

Vimspector needs two external bits before you can use it:
- a relevant [debug adapter](https://microsoft.github.io/debug-adapter-protocol/implementors/adapters/) (also called a *gadget*)
- a Vimspector config file

To **install a debug adapter**, run `:VimspectorInstall <adapter>`
You can use the *TAB* key to use auto-completion to see your options!

To **launch the debugger**, run `:call vimspector#Launch()`
This should reorient the panes/windows.

To **exit the debugger**, run `:call vimspector#Reset()`

Right now I've been playing around with:
- `vimspector#StepInto`
- `vimspector#StepOut`
- `vimspector#StepOver`
- `vimspector#ToggleBreakpoint`
- `vimspector#Continue`
## Resources
https://microsoft.github.io/debug-adapter-protocol/overview
DAP overview