## SELECT INTO

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
