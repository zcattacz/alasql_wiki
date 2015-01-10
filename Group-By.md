# SELECT GROUP BY

Grouping by columns:
```js
    var res = alasql('SELECT * FROM City GROUP BY Contient, Country');
```

Grouping by expressions:

```js
    var res = alasql('SELECT b FROM Nums GROUP BY a%2');
```

## Grouping functions
* CUBE()
* ROLLUP()
* GROUPING SETS()

```js
    alasql('SELECT * FROM City GROUP BY ROLLUP(Continent, Country)');
```

