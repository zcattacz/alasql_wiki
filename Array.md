# Keyword `ARRAY()`

`ARRAY()` Aggregator

This aggregator is used to aggregate all values into the array.

Syntax:
```
    ARRAY([DISTINCT] expression)
```

```js
    var res = alasql('SELECT userId, FIRST(userName) AS userName, \
          ARRAY({category:category,[count]:[count]}) AS purchases, \
          SUM([count]) AS totalCount FROM ? GROUP BY userId, userName',[data]);
```

See example [at jsFiddle](http://jsfiddle.net/agershun/5rte00j6/7/). For a real world example check out https://github.com/agershun/alasql/issues/827#issuecomment-283756454 .

The keyword can also be used like in this example 

    SELECT COLUMN a FROM test1 WHERE a = ANY (ARRAY[2,3,4])

