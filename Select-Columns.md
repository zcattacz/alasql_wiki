# SELECT columns

Columns
```sql
    SELECT size
    SELECT City.Name, City.Population
```
Expressions
```sql
    SELECT LCASE(City), 2+2
```
Aggregators
```sql
    SELECT COUNT(*), SUM(Population)
```

Alias
```sql
    SELECT City+” “+Country AS LongName
```
