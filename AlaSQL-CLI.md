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

Number of lines in text file with length more than 20 characters 

``` bash
alasql 'select value count(*) from txt("README.md") where length([0]) > 20'
```



Convert XLSX file to JSON

```bash
> alasql "SELECT * INTO json('my.json') from xlsx('cities.xlsx',{headers:true}) WHERE population > 20000000"
```

Simple calculator

``` bash
> alasql 'VALUE OF SELECT 2*2'
4
```

`?` will be replaced with the corresponding n'th argument so `alasql "select ?+?" 10 20` corresponds to `alasql select 10+20` 

```bash
> alasql "VALUE SELECT 20-?+?" 5 100
115
```

_(To get value instead of a JSON you can prepend [`VALUE OF`](Value) to the `SELECT`)_

