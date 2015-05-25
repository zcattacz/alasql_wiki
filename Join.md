# SELECT JOIN

## Join Types
Supported join types:
* [INNER] JOIN
* LEFT [OUTER] JOIN
* RIGHT [OUTER] JOIN
* [FULL] OUTER JOIN
* ANTI JOIN
* SEMI JOIN
* CROSS JOIN
* NATURAL JOIN

```js
    alasql('SELECT * FROM Cities JOIN Countries');
```

### JOIN USING
```js
    alasql('SELECT city.*, country.* FROM city \
                JOIN country USING countryid');
    alasql('SELECT * FROM Cities JOIN Countries USING Country');
```

### JOIN ON
```js
    alasql('SELECT city.*, country.* FROM city \
                JOIN country ON city.countryid = country.countryid');
    alasql('SELECT * FROM Cities JOIN Countries ON Citites.Country = Countries.Country');
```

### UNING and ON

Actually AlaSQL converts internally to the same execution plan, like in this example:

JOIN USING works fine in [this example](http://jsfiddle.net/agershun/na64p95k/1/)
```js
      var data = { COLORS: [[1,"red"],[2,"yellow"],[3,"orange"]],            
       "FRUITS":[[1,"apple"],[2,"banana"],[3,"orange"]]};

     data.NEW_FRUITS = alasql('SELECT MATRIX COLORS.[0], COLORS.[1], \
     FRUITS.[1] AS [2] FROM ? AS COLORS JOIN ? AS FRUITS USING [0]',
     [data.COLORS, data.FRUITS]);
 
```

With using JOIN ON in [this example](http://jsfiddle.net/agershun/Lxgfduov/):

```js
   var data = { COLORS: [[1,"red"],[2,"yellow"],[3,"orange"]],            
       "FRUITS":[[1,"apple"],[2,"banana"],[3,"orange"]]};

    data.NEW_FRUITS = alasql('SELECT MATRIX COLORS.[0], COLORS.[1], FRUITS.[1] AS [2] \
    FROM ? AS COLORS JOIN ? AS FRUITS ON COLORS.[0] = FRUITS.[0]',
    [data.COLORS,     data.FRUITS]);
```
