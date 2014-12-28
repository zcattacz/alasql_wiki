## SELECT INTO

Into table
```js
    alasql('SELECT * INTO City FROM Capital');
    alasql('SELECT * INTO AfrikanCountries FROM Countries WHERE Country = "Afrika"');
```

Into external file (into-functions)
```js
    alaslq('SELECT * INTO CSV(‘city.csv’) FROM City');
```

Into stdout (for Node.js):
```js
    alasql('SELECT * INTO TXT() FROM City');
```

## INTO-functions
* TXT()
* JSON()
* CSV()
* TSV() / TAB()
* XLSX()
* HTML()

Example of data format conversion from XLSX to CSV:
```js
    alasql('SELECT * INTO CSV("parts.csv") FROM XLSX("parts.xlsx") WHERE Qty > 10');
    alasql('SELECT * INTO TXT("cities.txt") FROM cities');
```
