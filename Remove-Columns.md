# REMOVE COLUMNS

Sometimes you may want to select all fields but without some of them. 

For example:
```js
    var data = [{a:1,b:10},{a:2,b:20}];
    var res = alasql('SELECT * REMOVE COLUMN b FROM ?',[data]);
    // returns [{a:!},{a:2}]
```

You can also remove group of columns with ```LIKE``` clause:
```sql
    SELECT * REMOVE COLUMNS LIKE '%a%',b,c FROM one
```

With [Angular.js](Angular.js) AlaSQL automatically remove ```$$hashKey``` (see [this example](http://jsfiddle.net/agershun/efmhcnu8/1/))



