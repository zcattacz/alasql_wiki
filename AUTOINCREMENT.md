# Keyword `AUTOINCREMENT`

Define default value for the column with auto incremeting.

Syntax:
```sql
    CREATE TABLE tableid (
         columnid typeid AUTOINCREMENT,...
    )
```

Has the alias `AUTO_INCREMENT` for support of varius native databases.

To get the last inserted auto_increment value please access `alasql.autoval(tablename, colname)`. 
To get the next value to be inserted into an auto_increment field please access `alasql.autoval(tablename, colname, true)`. Please note that for async operations the values can be altered by other queries and therefore might not reflect what you expect.


See also: [IDENTITY](Identity)