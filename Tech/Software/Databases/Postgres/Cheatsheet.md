---
aliases: 
created: 2022-02-24, 2:29:20 pm (Thursday, February 24th)
updated: 2022-04-26, 10:03:39 am (Tuesday, April 26th)
---
## Login
To the default table:
`psql postgres`

## Create a "user" (role)
`CREATE ROLE <name> WITH <options> PASSWORD <pw>`

[Source](https://www.postgresqltutorial.com/postgresql-roles/)

## Get help
`\?`

Can search with `/`

Example, searching for how to find all dbs:
- `\?`
- `/database`
- see that `\l` can list all dbs