# SET variable value

### Set options
Set option or variable to the value. 
```js
    alasql('SET AUTOCOMMIT ON');
    alasql('SET AUTOCOMMIT OFF');
    alasql('SET MODIFIER = "RECORDSET"');
```

### Set local variables
You can set local variables with ```@``` prefix as well:

```sql
    SET @data = @[{a:1},{a:2}];
```

### Set parameter variables:
```sql
    SET $one = 10;
```

### Set properties of local variables
```sql
    SET @a->b->(c+d)->(0) = 2+2;
```
