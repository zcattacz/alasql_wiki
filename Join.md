## SELECT JOIN

```js
    alasql('SELECT * FROM Cities JOIN Countries');
```

### JOIN ON
```js
    alasql('SELECT * FROM Cities JOIN Countries ON Citites.Country = Countries.Country');
```

### JOIN USING
```js
    alasql('SELECT * FROM Cities JOIN Countries USING Country');
```