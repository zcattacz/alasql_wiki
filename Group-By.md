# SELECT GROUP BY

Grouping
```js
    var res = alasql('SELECT * FROM City GROUP BY Contient, Country');
```

## Grouping functions
* CUBE()
* ROLLUP()
* GROUPING SETS()

```js
    alasql('SELECT * FROM City GROUP BY ROLLUP(Continent, Country)');
```

