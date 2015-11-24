# Keyword `ROW`


Syntax:
```sql
    ROW OF SELECT ...
```

Alternative syntax:
```sql
    SELECT ROW ...
```


Usually AlaSQL returns array of records (JavaScript objects), but you can modify SELECT statement to return an array of values from first row selected.


You can set query modifier for all SELECTs:
```js
    alasql.options.modifier = 'ROW';
```



See also: [VALUE](Value), [MATRIX](Matrix), [COLUMN](Column), [ROW](Row), [RECORDSET](Recordset)