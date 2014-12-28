## TOP

Select top 10 records of data table:
```js
    alasql('SELECT TOP 10 * FROM Cities ORDER BY Name');
```
Select top 10 records of array:
```js
    var data = [];
    for(var i=0;i<100;i++) data.push({num:i});
    var res = alasql('SELECT TOP 10 * FROM ?',[data]);
```