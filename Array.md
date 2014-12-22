## ARRAY() Aggregator


```js
    var res = alasql('SELECT userId, FIRST(userName) AS userName, \
          ARRAY({category:category,[count]:[count]}) AS purchases, \
          SUM([count]) AS totalCount FROM ? GROUP BY userId, userName',[data]);
```

See example [at jsFiddle](http://jsfiddle.net/agershun/5rte00j6/7/)