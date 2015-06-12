# Alacon 

Alacon is AlaSQL in a console

Examples:

1. Number of lines in text file with length more than 20 characters 

```
   alacon 'select value count(*) from txt("README.md") where length([0]) > 20'
```

2. Simple calculator

```
    alacon '2*2'
```

3. Convert XLSX file to JSON

```
    alacon "select * into json('my.json') from xlsx('cities.xlsx',{headers:true})"
```

Please see [install notes](install) on how to install.