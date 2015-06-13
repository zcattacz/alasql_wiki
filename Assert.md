# Keyword `ASSERT`

Throws a javascript error if result of last operation is not equal to value (AlaSQL uses equalDeep() function for comparision)

Syntax:
```sql
    ASSERT [message,] value;
```
For example:

```js
    alasql('ASSERT 1');
    alasql('ASSERT “Wrong Value”, @[{a:1,b:”Odessa”}]');
```

You can use AlaSQL ASSERT operator to test results of previous operation:
```sql
    ASSERT string | number | boolean | array | object
```

For example:
```sql
    CREATE TABLE one (a INT);
    ASSERT 1;
    INSERT INTO one VALUES (1),(2),(3);
    ASSERT 3;
    SELECT * FROM one ORDER BY a DESC;
    ASSERT [{a:3},{a:2},{a:1}];
```

ASSERT statement uses regular JSON notation for the object.