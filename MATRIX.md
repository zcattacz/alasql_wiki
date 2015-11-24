# Keyword `MATRIX`

result modifier for a `SELECT` 


Syntax:
```sql
    MATRIX OF SELECT ...
```

Alternative syntax:
```sql
    SELECT MATRIX ...
```


Usually AlaSQL returns array of records (JavaScript objects), but you can modify SELECT statement to return a matrix (array of arrays) of values from the recordset. Row order is as requested in the select.


You can set query modifier for all SELECTs:
```js
    alasql.options.modifier = 'MATRIX';
```

 

See also: [RECORDSET](Recordset), [VALUE](Value), [ROW](Row), [COLUMN](Column)