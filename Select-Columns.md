# Keyword `SELECT`

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

Select all columns from table
```sql
    SELECT *, City.*
```
Select columns of arrays
```sql
    SELECT [0],[1] 
```
Column names with spaces, etc
```sql
    SELECT [My Column]   -- SQL Server style
    SELECT `My Column`   -- MySQL style
```