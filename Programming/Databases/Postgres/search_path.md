Sometimes you'll look for a table with `\dt` and not see anything but will see something using:
```
SELECT *
FROM pg_catalog.pg_tables
WHERE schemaname != 'pg_catalog' AND 
    schemaname != 'information_schema';
```

This may be because something's not in your `search_path`.

