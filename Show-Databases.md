# Keyword `SHOW DATABASES`

List of all databases in memory.

Syntax:
```sql
    SHOW DATABASES [LIKE pattern]
```

For example:
```js
    var res = alasql("SHOW DATABASES LIKE ‘A%’");
```

See also: [SHOW](Show)