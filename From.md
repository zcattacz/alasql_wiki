## SELECT FROM

From database table
```js
    alasql('SELECT * FROM albums');
    alasql('SELECT * FROM mydb.test');
```
From parameter
```js
    alasql(‘SELECT * FROM ?’,[singers]);
```

From array parameter
```js
    alasql(‘SELECT * FROM [?]’,[singers]);
```

From file (FROM-function)
```js
    alasql('SELECT * FROM XLSX(“medals.xlsx”)');
```

From stdin (for Node.js)
```js
    alasql('SELECT * FROM TXT()');
```

From SELECT statement
```js
    alasql('SELECT * FROM (SELECT * FROM  (SELECT * FROM City))');
```

## From functions
* TXT()
* JSON()
* CSV()
* TSV() / TAB()
* XLSX() / XLS()
* HTML()

## From parameters (? and [?])

* ? – just value
* [?] – converts array to array of arrays

```js
    [1,2,3] => [[1],[2],[3]]
```

## Table Alias
FROM  table alias

```js
    alasql('SELECT * FROM ? City');
    alasql('SELECT * FROM album AS a');
```

Examples:

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