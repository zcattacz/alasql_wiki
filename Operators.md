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
- `property->functionName(args)`  equals `property["functionName"](args)` in javascript


Object property
* `a -> b`
* `a -> b -> c`

Array member
* `a -> 1`
* `a -> 1 -> 2`

Calculated property name
* `a -> (1+2)`
* `a -> ("text2 + " " + "more")`

Functions
* `myTime -> getFullYear()`
* `s -> substr(1,2)`


Arrow function -> property
```js
    var data = [{a:{b:1,c:1}, {a:{b:2}}}]
    alasql(‘SELECT a->b as val FROM ?’,[data]);
    // [{val:1},{val:2}]
```

Array members
```sql
    SELECT a->(0) FROM data
```

Calculated property names
```sql
    SELECT a->(“mon”+moid), b->(2+2) FROM data
```

JavaScript string functions can also be used

```sql
    SELECT s->length FROM mytext
```
