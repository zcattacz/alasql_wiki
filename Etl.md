You can use Alasql and [Alacon](Alacon) for simple ETL procedures.

## Load data from CSV file with headers
If you have a CSV file, you can process it directly in Alasql: 

```js
    alasql('select * from csv("cities.csv",{headers:true}) where population > 100000 order by city', [],
      function(data) {
         console.log(data);
    });
```

You can do the same query with [Alacon](Alacon) command-line utility and prepare file to stdout:
```
    node alacon "select * from csv('cities.csv',{headers:true}) where population > 100000 order by city" >city.txt
```

## Prepare data from Excel file (see [XLSX()](Xlsx) function):
```js
    alasql('select * from xlsx("cities.xlsx",{headers:true, range:"A1:E100"})\
      where population > 100000 order by city', [], function(data) {
         console.log(data);
    });
```


