# Keyword `VALUE`

Syntax:
```sql
    VALUE OF SELECT ...
```

Alternative syntax:
```sql
    SELECT VALUE ...
```


Usually AlaSQL returns array of records (JavaScript objects), but you can modify SELECT statement to return single value from the first line and first column of result recordset:
```js
    var data = [{a:1},{a:2}];
    var res = alasql('VALUE OF SELECT SUM(a) FROM ?',[data]);
    // returns 3

    var res = alasql('SELECT COUNT(*) FROM ?',[data]);
    // returns [{'COUNT(*)':2}]
    
   var res = alasql('SELECT VALUE COUNT(*) FROM ?',[data]);
    // returns 2


```

See also: [MATRIX](Matrix), [COLUMN](Column), [ROW](Row), [RECORDSET](Recordset)
