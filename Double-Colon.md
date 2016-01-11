# `::` double-colon type conversion

AlaSQL supports ```::``` operator:

```js
   alasql('SELECT '10/12/2013'::DATE');
```

To cast types to Number you can use one of three forms:
```sql
    SELECT CAST(a AS NUMBER), FORMAT(NUMBER,a), a::NUMBER 
```
