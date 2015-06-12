# Keyword `DISTINCT`

Is used in combination with [`SELECT`](Select) and aggregators.

Syntax:
```sql
    SELECT DISTINCT ...
    aggregator (DISTINCT expression)
    SEARCH DISTINCT(selector)
```
Select distinct values from result array:
```js
    alasql('SELECT DISTINCT MID(Name,1,1) FROM City');
```

See also: [DISTINCT][Distinct]