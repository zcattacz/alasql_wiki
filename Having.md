# SELECT HAVING

Filtering groups
```js
    var res = alasql('SELECT *, COUNT(*) AS cnt FROM City \
                GROUP BY Country HAVING cnt > 2');
```
