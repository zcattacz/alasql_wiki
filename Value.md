# VALUE

Usually AlaSQL returns array of records (JavaScript objects), but you can modify SELECT statement to return single value from the first line and first column of result recordset:
```js
    var data = [{a:1},{a:2}];
    var res = alasql('SELECT COUNT(*) FROM ?',[data]);
    // returns [{'COUNT(*)':2}]
    var res = alasql('SELECT VALUE COUNT(*) FROM ?',[data]);
    // returns 2
```
