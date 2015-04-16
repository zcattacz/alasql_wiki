# SELECT ORDER BY

Ascending:
```js
    alasql('SELECT * FROM City ORDER BY Population');
    alasql('SELECT * FROM City ORDER BY Population ASC');
```

Descending:
```js
    alasql('SELECT * FROM City ORDER BY Name DESC');
```

### Number notation for ORDER BY

AlaSQL supports number notation for ORDER BY arguments:
```js
    var data = [{a:2,b:20},{a:2,b:30},{a:3,b:10}];
    var res1 = alasql('SELECT a,b FROM ? ORDER BY 2,1',[data]);
    var res2 = alasql('SELECT a,b FROM ? ORDER BY 1 DESC,2 DESC',[data]);
```