# Keyword `UPDATE`


Syntax:
```sql
    UPDATE table SET prop1 = value1, ... WHERE condition
```

For example:

```js
alasql("UPDATE events SET synchronized = ? WHERE name = ?", [true, event.name]);

alasql('UPDATE cities SET population = population * 1.5 WHERE name LIKE "A%"');

alasql('UPDATE city SET population = LEN(name) * 1000000 WHERE name LIKE "M%"');
```



See also: [DELETE](Delete), [INSERT](Insert)