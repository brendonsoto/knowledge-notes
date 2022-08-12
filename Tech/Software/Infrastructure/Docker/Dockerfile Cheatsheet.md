---
aliases: 
created: 2022-08-12, 2:23:28 pm (Friday, August 12th)
updated: 2022-08-12, 2:24:19 pm (Friday, August 12th)
---
`WORKDIR /path`
This will create the given path if it doesn't exist and use it as the main directory for everything else.
This means any `COPY` commands will use the `WORKDIR` path as the target path to copy files to.