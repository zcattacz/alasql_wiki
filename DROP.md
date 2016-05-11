# Keyword `DROP`

Keyword for dropping databases, tables, views, columns, and indexes.

Syntax:
```sql
    DROP [engine] DATABASE alias;
    DROP TABLE table;
    ALTER TABLE table DROP COLUMN columnid;
    DROP INDEX index;
```

Note that `[engine]` is to be used when the database to be `DROP`ed is hosed by a different engine. Example: 

```sql
DROP INDEXEDDB DATABASE db_name
```

See also: [DROP DATABASE](Drop Database), [DROP TABLE](Drop Table), [DROP COLUMN](Drop Column), [DROP INDEX](Drop Index)