---
aliases: 
created: 2022-01-17, 3:57:55 pm (Monday, January 17th)
updated: 2022-01-17, 4:02:21 pm (Monday, January 17th)
---
Time in templates is really weird.
The `now` function provides the current time.
**Formatting** is based off of providing sub-parts of a specific date: `01/02 03:04:05PM '06 -0700`
In an ordered list:
1. Month
2. Day
3. Time (Hour)
4. Time (Seconds)
5. Time (MiliSeconds in two decimal places)
6. Year
7. Timezone

I hate it.

In order to get the current hour and minutes: `now | date '03:04'`

## Sources
- [A blog explaining why](https://www.pauladamsmith.com/blog/2011/05/go_time.html)
- [Sprig docs](https://masterminds.github.io/sprig/date.html)