# Operators

Operators you can use with AlaSQL

**Number**
```
    +,-,*,/
```

**String**
```
    +
```

**Logic**
```sql
    AND, OR, NOT
    =, !=, >, >=, <, <=
```

### Complex operators

**SQL related**

```sql
    v BETWEEN a AND b
    v NOT BETWEEN a AND b
    v IN (10,20,30)
    v NOT IN (SELECT * FROM Ages)
    v >= ANY (20,30,40)
```


**Deep Equal Operator**
```sql
    SELECT @{a:1} == @{a:1}
    => True

    SELECT * FROM one WHERE a=1
    INSERT INTO one VALUES {a:[5,6]}
    SELECT * FROM one WHERE a==@[5,6]
```

**Access a child**

The `->` operator is inspired by the structure-pointer member operator in C/C++ and the object member operator in C++/Perl/PHP and is used in AlaSQL to access nested data.

- `property->text` equals `property["text"]` in javascript 
- `property->number` equals `property[number]` in javascript 
- `property->functionName(args)`  equalis `property["functionName"](args)` in javascript