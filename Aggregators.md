# Aggregators

## SQL Standard
* SUM()
* AVG()
* COUNT()
* MAX()
* MIN()
* FIRST()
* LAST()

Examples:
```sql
    SELECT COUNT()
    SELECT COUNT(one)
    SELECT COUNT(*)
````

## Non-standard 
* AGGR() – operations on aggregated values
* ARRAY() – create array of values
* User-defined aggregators

Examples:
```sql
    SELECT SUM(a) AS sm, COUNT(*) AS cnt, AGGR(sm/cnt) AS avg1, AVG(a) AS avg2 FROM data
```

