---
aliases: 
created: 2022-01-17, 5:46:15 pm (Monday, January 17th)
updated: 2022-01-17, 5:47:53 pm (Monday, January 17th)
---
The template syntax can add whitespace.
To get rid of it, use `-` next to the curly brackets for whatever side you want to remove whitespace from.

For example, `{{- template "my_template" }}` removes whitespace from the left side but *not* the right side.

## Sources
- [Docs](https://www.chezmoi.io/docs/templating/#removing-whitespace))

## Related
- [[Tech/Software/Chezmoi/Templates/Syntax]]