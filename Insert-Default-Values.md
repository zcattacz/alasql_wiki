# Keyword `DEFAULT VALUES`

Syntax:
```sql
    INSERT INTO tableid DEFAULT VALUES;
```
For example:
```js
   alasql('CREATE TABLE Orders (OrderNo INT DEFAULT 1, Desc STRING DEFAULT "Something")');
   alasql('INSERT INTO Orders DEFAULT VALUES');
```

See also: [DEFAULT](Default), [INSERT](Insert)