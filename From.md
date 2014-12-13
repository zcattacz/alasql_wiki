## SELECT FROM

```js
    alasql('SELECT * FROM cities');
```

```js
    var data = [{city:"Boston"}, {city:"Los Angeles"}];
    alasql('SELECT * FROM ? ORDER BY city',[data]);
```

You can also get data from stdin stream (for Node.js only). For example, how to calculate
number of lines in incoming text file:
```js
    alasql('SELECT COUNT(*) FROM TXT()');
``` 