# How to SQL group by non aggregate condition?

Source: [Stackoverflow.com](http://stackoverflow.com/questions/28130749/sql-group-by-non-aggregate-condition)

### Question

s it possible to have non-aggregate condition on groups? For example we have:
```
    Table1(firstName, lastName, gender)
```
And we group by firstName and then by lastName, but we want only the groups having at least 5 males in it. 

### Answer

```sql
    SELECT * 
        FROM people 
        GROUP BY FirstName, LastName 
        HAVING SUM(CASE WHEN Gender = "M" THEN 1 ELSE 0 END) >= 5 
```

See the working AlaSQL example [in jsFiddle](http://jsfiddle.net/cutu8uwe/2/)