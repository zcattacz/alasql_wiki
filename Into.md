# Keyword `INTO`

Syntax:
```sql
    SELECT ... INTO (table|into-function);
    INSERT INTO table VALUES value1, value2, ...;
```

## INTO-functions
* [[TXT]]()
* [[JSON]]()
* [[CSV]]()
* [[TSV]]()
* [[TAB]]()
* [[XLSX]]()
* [[HTML]]()

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

### Into parameter array
You can save data into parametes array. In this case AlaSQL append records to existing array:
```js
    var data = [{a:1},{a:2}]; // Source array
    var resdata = [{a:0}];    // Destination array
    var res = alasql('SELECT * INTO ? FROM ? WHERE a<1',[resdata,data]); 
```
AlaSQL returns in ```res``` == 1 - number or records and ```resdata``` equals to ```[ { a: 0 }, { a: 2 } ]```


Example of data format conversion from XLSX to CSV:
```js
    alasql('SELECT * INTO CSV("parts.csv") FROM XLSX("parts.xlsx") WHERE Qty > 10');
    alasql('SELECT * INTO TXT("cities.txt") FROM cities');
```





See also: [FROM](From)