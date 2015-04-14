# Subqueries

You can use SELECT operator as a part of SQL expressions, like:
```js
    var res = alasql('SELECT * FROM phases q WHERE (SELECT COUNT(*) \
        FROM phases t WHERE t.Phase = q.Phase) = 2');
```

AlaSQL converts array to single value (like [VALUE](Value) modifier does) before usage in expression.

See working example [in jsFiddle](http://jsfiddle.net/agershun/zr3ovm7y/1/)
