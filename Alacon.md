# Alacon 

Alacon is AlaSQL in a console

_Please note that from version 0.2.0 the command will be called `alasql` instead of `alacon`_

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

Please see [install notes](install) on how to install.