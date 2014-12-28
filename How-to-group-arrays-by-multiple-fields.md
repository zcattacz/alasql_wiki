# How to group arrays by multiple fields?

Source: [StackOverflow.com](http://stackoverflow.com/questions/25332180/multiple-grouping-a-json-object/27618648#27618648)

### Question

How to get a new JSON object from this:
```sql
`    (group by "a" & group by "b" field with sum "d" and with count(objects))`
```
```js
    var json = [
        {"a":121, "b":212, "c":"0", "d":100},
        {"a":121, "b":212, "c":"0", "d":300},
        {"a":121, "b":210, "c":"0", "d":200},
        {"a":120, "b":210, "c":"0", "d":300}
        ];
        
    var new_json = [
        {"a":121, "b":212, "c":"0", "d":400, "count":2},
        {"a":121, "b":210, "c":"0", "d":200, "count":1},
        {"a":120, "b":210, "c":"0", "d":300, "count":1}
        ];
```

### Answer

You can do it with Alasql library:

    var res = alasql('SELECT a,b,c,SUM(d) AS d,COUNT(*) AS [count] FROM ? \
                      GROUP BY a,b,c',[json]);

Try this example [at jsFiddle](http://jsfiddle.net/agershun/2u54cpuy/1/). 
