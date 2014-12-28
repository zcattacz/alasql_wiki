## SELECT INTO

Into table
```js
    alasql('SELECT * INTO City FROM Capital');
```

Into external file (into-functions)
```js
    alaslq('SELECT * INTO CSV(‘city.csv’) FROM City');
```

Into stdout (for Node.js):
```js
    alasql('SELECT * INTO TXT() FROM City');
```

## Into-functions
* TXT()
* JSON()
* CSV()
* TSV() / TAB()
* XLSX()
* HTML()

Examples:

```js
    alasql('SELECT * INTO AfrikanCountries FROM Countries WHERE Country = "Afrika"');
```

```js
    alasql('SELECT * INTO TXT("cities.txt") FROM cities');
```

Data format conversion (from XLSX to CSV):
```js
    alasql('SELECT * INTO CSV("parts.csv") FROM XLSX("parts.xlsx") WHERE Qty > 10');
```
