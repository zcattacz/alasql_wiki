# Operators

Number
```
    +,-,*,/
```
String
```
    +
```
Logic
```sql
    AND, OR, NOT
    =, !=, >, >=, <, <=
```

Complex 
```sql
    v BETWEEN a AND b
    v NOT BETWEEN a AND b
    v IN (10,20,30)
    v NOT IN (SELECT * FROM Ages)
    v >= ANY (20,30,40)
```

## Deep Equal Operator
```sql
    SELECT @{a:1} == @{a:1}
    => True

    SELECT * FROM one WHERE a=1
    INSERT INTO one VALUES {a:[5,6]}
    SELECT * FROM one WHERE a==@[5,6]
```

