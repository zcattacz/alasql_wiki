# DATE

AlaSQL supports two different date types:
* Date - JavaScript date type (object)
* DATE - SQL date type (string like 'YYYYMMDD')

See the example:
```js
    alasql('CREATE TABLE orders (orderdate Date)');
    alasql('INSERT INTO orders VALUES ("2014-01-01")');
    var res = alasql('SELECT * FROM orders');
    // It gives a JavaScript dates
    var res = alasql('SELECT orderdare->getUTCFullYear() FROM orders');
    // This is gives an array of years
    // Here - getUTCFullYear() - is a function of object Date.prototype
```

If you want ot use good old SQL date just use DATE, instead Date:
```js
    alasql('CREATE TABLE sample (sqldate DATE, jsdate Date)');
```
See a [jsFiddle example](http://jsfiddle.net/b94d5e3w/)



Please note that Javascript will use locale when working with dates, so make sure always to ask for UTC time. Example: for the Date `2014-01-01` the `.getFullYear()` (missing `UTC`) will give you `2013` if you are located west of london. 

