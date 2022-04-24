---
aliases: 
created: 2022-01-16, 7:38:31 am (Sunday, January 16th)
updated: 2022-01-16, 8:16:49 am (Sunday, January 16th)
---

## Boolean
- `eq`
- `not`
- `and`
- `or`

## Integer
- `len`
- `eq`
- `ne`
- `lt`
- `le`
- `gt`
- `ge`

## Example
From the docs
```
{{ if (eq .chezmoi.os "darwin") }}
# darwin
{{ else if (eq .chezmoi.os "linux" ) }}
# linux
{{ else }}
# other operating system
{{ end }}
```

## Resources
- [docs](https://www.chezmoi.io/docs/templating/#simple-logic)

## Related
- [[Tech/Software/Chezmoi/Templates/Available data]]
- [[Tech/Software/Chezmoi/Templates/Syntax#For conditionals]]ssss