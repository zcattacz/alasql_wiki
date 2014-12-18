## Alacon Samples

1. Number of lines in text file with length more than 20 characters 
```
    node alacon 'select value count(*) from txt("README.md") where length([0]) > 20'
```

2. Simple calculator
```
    node alacon '2*2'
```

3. Convert XLSX file to JSON
```
    node alacon "select * into json('my.json') from xlsx('cities.xlsx',{headers:true})"
```