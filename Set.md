# SET variable value

### Set options
Set option or variable to the value. Currently is used only for [Local Storage](LocalStorage) external database.
```js
    alasql('SET AUTOCOMMIT ON');
    alasql('SET AUTOCOMMIT OFF');
```

### Set local variables

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
