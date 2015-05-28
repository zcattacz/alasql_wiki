## INSERT SELECT

Syntax:
```sql
    INSERT INTO tableid SELECT query
```

```js
    alasql('INSERT INTO AsianCities \
               SELECT * FROM Cities WHERE Continent = "Asia"');
```

See also: [INSERT](Insert), [SELECT](Select)