# RECORDSET

AlaSQL modifier for SELECT queries.
```sql
    SET @data = @[{a:1,b:10},{a:2,b:20}];
    SELECT a, b FROM @data;
    // returns array of objects [{a:1,b:10},{a:2,b:20}]

    SELECT RECORDSET a, b FROM @data;
    // returns array of objects {data:[{a:1,b:10},{a:2,b:20}], 
          columns:[{columnid:'a'},{columnid:'b'}]}
```
You can change also query modifier with AlaSQL options:
```js
    alasql.options.modifier = 'RECORDSET';
```
By default, all nestes subqueries returns data as Recordset.
