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
