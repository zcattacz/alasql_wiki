# Keyword `IF`

Conditional statement.

Syntax:
```sql
    IF expression THEN statement1 [ELSE statement2]
```

See also: [CASE](Case)

## Return one of two values

You can use the MySQL notation 

```
SELECT IF(1>2,2,3);
       -> 3
```

or ghe MsSQL notation

```
SELECT IIF(1>2,2,3);
       -> 3
```

to select one out of two values. 