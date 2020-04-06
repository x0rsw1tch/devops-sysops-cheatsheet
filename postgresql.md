# PostgreSQL Cheatsheet

### Create backup of Database

```
pg_dump DBNAME > /path/to/file.sql
```
---


### Restore database from backup
```
psql
CREATE DATABASE "dbname" WITH OWNER = owner OTHER PARAMETERS;
\q
psql -d dbname -f /opt/dotcms2.sql
```

### Dump table as SQL commands (optional output to file)
```
pg_dump --table=export_table --data-only --column-inserts my_database > data.sql
```