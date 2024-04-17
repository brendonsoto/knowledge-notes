---
tags: 
- database
created: Thursday, April 11, 2024 2:53 PM
created_at: 2024-04-11T14:53:54-04:00
---
## Relationships

If you have a *one-to-one* or *one-to-many* relationship between two tables, it's okay then to use a foreign key directly in the schema. For an example, think about car manufacturers and types of cars. You can have a `manufacturer` table that features information only about the manufacturer (e.g. name, country, age, etc.).  You can then have a `cars` table where one of the columns can be a foreign key to the `manufacturer` table.

If you have a *many-to-many* relationship between two tables you'll want to use a [link/bridge table](Link%20and%20Bridge%20tables.md). That's a table the associates data from one table to another.