# Extract, transform and load with AlaSQL

You can use AlaSQL and [Alacon](Alacon) for ETL procedures.

## Load data from [CSV](Csv) file with headers
If you have a CSV file, you can process it directly in AlaSQL: 

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

## Prepare data from [XLSX](Xlsx) and XLS file
```js
    alasql('select * from xlsx("cities.xlsx",{headers:true, range:"A1:E100"})\
      where population > 100000 order by city', [], function(data) {
         console.log(data);
    });
```


