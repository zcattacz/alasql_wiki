## INSERT SELECT

Syntax:
```sql
    INSERT INTO tableid SELECT query
```

```js
    alasql('INSERT INTO AmericanCities \
               SELECT * FROM Cities WHERE Continent = "America"');
```

See also: [INSERT](Insert), [SELECT](Select)