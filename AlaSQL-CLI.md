# AlaSQL CLI 


AlaSQL can be used in a console by installing it globally: `npm install alasql -g` 


```
Usage:
  alasql "sql-statement" [ params ]        - Run SQL statement
  alasql --file file.sql [ params ]        - (or -f) Run SQL from file
  alasql --version                         - (or -v) Echo AlaSQL version
Samples:
  alasql 'select 2+2'
  alasql 'select count(*) from txt()' < city.txt
  alasql 'select * into xlsx("city.xlsx") from txt("city.txt")'
```




Examples:

1. Number of lines in text file with length more than 20 characters 

```
   alasql 'select value count(*) from txt("README.md") where length([0]) > 20'
```

2. Simple calculator

```
    alasql '2*2'
```

3. Convert XLSX file to JSON

```
    alasql "select * into json('my.json') from xlsx('cities.xlsx',{headers:true})"
```


You can place `?` in the code. They will be replaced by the n'th parameter so `alasql "select ?+?" 10 20` corresponds to `alasql select 10+20` 