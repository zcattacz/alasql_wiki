# AVG

AlaSQL supports AVG aggregator. 

For example:
```js
    var data = [{a:1, b:100},{a:2, b:90},{a:3, b:80},
           {a:4, b:70},{a:5, b:60},{a:6, b:50},
            {a:7, b:40},{a:8, b:30},{a:9, b:20},
            {a:10, b:10}];

    var res = alasql('SELECT COUNT(*), SUM(a), AVG(a),\
         SUM(b), AVG(b) FROM ?',[data]);
```

You can try this example [in jsFiddle](http://jsfiddle.net/agershun/7yxy6frz/)

**Note:** AlaSQL (like other SQL implementations) does not take in account ```NULL``` (undefined) values.

You can use AVG like other aggregators with ```DISTINCT``` keyword:
```sql
    SELECT AVG(DISTINCT age) FROM people
```