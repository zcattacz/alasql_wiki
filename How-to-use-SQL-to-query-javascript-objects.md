# How to use SQL to query javascript objects?

Source: [StackOverflow.com](http://stackoverflow.com/questions/5327088/use-sql-to-query-javascript-objects?lq=1)
### Question

Is there a way to run an SQL query against javascript objects to find data within them? Specifically I'm looking for a way to query a few objects (each representing a table of data) and perform a join on them.

### Answer

AlaSQL is a JavaScript SQL data manipulating library and supports SQL syntax.

This is an example:
```js
    var data = [{ dep: 'A', qt: 10, price: 5}, { dep: 'A', qt: 5,  price: 2.30 },
                { dep: 'B', qt: 3,  price: 2.20 }, { dep: 'C', qt: 1,  price: 4 },
                { dep: 'C', qt: 4,  price: 10 }];

    var res = alasql('SELECT dep, SUM(qt) AS qt, SUM(qt*price) AS amt, \
                          FROM ? GROUP BY dep',[data]);
```
Try this example [in jsFiddle][2].


  [1]: http://alasql.org
  [2]: http://jsfiddle.net/agershun/L8471bnk/