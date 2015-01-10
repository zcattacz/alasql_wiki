# SELECT HAVING

Filtering groups by expressions:

For example, select countries with number of cities > 2:

```js
    var res = alasql('SELECT *, COUNT(*) AS cnt FROM City \
                GROUP BY Country \
                HAVING cnt > 2');
```

Expressions can contain aggregators, like below:

```js
    var res = alasql('SELECT * FROM City \
                GROUP BY Country \
                HAVING COUNT(*) > 2');
```
