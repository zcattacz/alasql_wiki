# DATE

AlaSQL supports two different date types:
* Date - JavaScript date type (object)
* DATE - SQL date type (string like 'YYYYMMDD')

See the example:
```js
    alasql('CREATE TABLE orders (orderdate Date)');
    alasql('INSERT INTO orders VALUES ("2014-01-01")');
    var res = alasql('SELECT * FROM orders");
    // It gives a JavaScript dates
    var res = alasql('SELECT orderdare->getFullYear() FROM orders');
    // This is gives an array of years
    // Here - getFullYear() - is a function of object Date.prototype
```

If you want ot use good old SQL date just use DATE, instead Date:
```js
    alasql('CREATE TABLE sample (sqldate DATE, jsdate Date)');
```
