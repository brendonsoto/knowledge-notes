---
aliases: 
tags:
  - the-rust-programming-language
  - unix
created: Wednesday, September 20, 2023 2:33 PM
created_at: 2023-09-20T14:33:05-04:00
updated: 2023-09-20, 2:34:22 pm (Wednesday, September 20th)
---
## Conditionals

```
if [ 1 -gt 0 ]; then
  echo "1 is greater than 0"
else
  echo "1 is less than 0"
fi
```

For what conditions you can use, check `man test`.

## Variables - local
```
local myVar="A local var"
local theDate
theDate=$(date)

echo "$myVar"
echo "$theDate"
```
