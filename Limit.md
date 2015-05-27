# LIMIT

Limit the number of records from result set.

Syntax:
```sql
    SELECT ... LIMIT number FETCH number
```

For example, select 20 records starting from record number 5
```js
    alasql('SELECT * FROM Cities ORDER BY Name LIMIT 20 FETCH 5');
```

See also: [TOP](Top), [FETCH](Fetch)
