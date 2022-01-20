---
aliases: 
created: 2022-01-16, 8:26:57 am (Sunday, January 16th)
updated: 2022-01-16, 8:28:59 am (Sunday, January 16th)
---
## For templates without custom args
With a file: `cat dot_example.tmpl | chezmoi execute-template`

With string: `chezmoi execute-template '{{ .chezmoi.hostname }}'`

## For templates with custom args
#to-do
## Resources
- [docs](https://www.chezmoi.io/docs/how-to/#use-templates)