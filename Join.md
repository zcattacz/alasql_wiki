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
