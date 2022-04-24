---
aliases: 
created: 2022-01-16, 7:45:20 am (Sunday, January 16th)
updated: 2022-01-16, 7:50:04 am (Sunday, January 16th)
---

Chezmoi's syntax is like the [mustache templating lang](https://mustache.github.io/):
`{{ .chezmoi.hostname }}`

Double curly bracket with content inside.

## For conditionals
```
{{ if <conditional> <arg1> <arg2> }}
Stuff to include if cond is true
{{ end }}
```
## Resources
- [Docs](https://www.chezmoi.io/docs/templating/#template-syntax)

## Related
- [[Tech/Software/Chezmoi/Templates/Available data]]
- [[Tech/Software/Chezmoi/Templates/Logic]]