# GROUP BY

Syntax:
```sql
    SELECT ... GROUP BY expression, expression...
    SELECT ... GROUP BY CUBE(expression,...) | ROLLUP(expression,...) | GROUPING SETS(expression,...)  
```
Grouping by columns:
```js
    var res = alasql('SELECT * FROM City GROUP BY Contient, Country');
```

Grouping by expressions:

```js
    var res = alasql('SELECT b FROM Nums GROUP BY a%2');
```

The example:
```js
    alasql('SELECT projects, FIRST(duration) AS duration, \
        FIRST([path]) AS [path], FIRST(application) AS application  \
        FROM json("timing_output") \
        GROUP BY projects, duration, [path], application \
        ORDER BY duration DESC',[],function(res){
          console.log(res);
    });
```
Try this example in [jsFiddle](http://jsfiddle.net/j39agf7c/1/)

## Grouping functions
* [CUBE()](Cube)
* [ROLLUP()](Rollup)
* [GROUPING SETS()](Grouping Sets)

```js
    alasql('SELECT * FROM City GROUP BY ROLLUP(Continent, Country)');
```
See [jsFiddle example](http://jsfiddle.net/agershun/1nccgs6n/2/) for ROLLUP(), CUBE(), and GROUPING SETS().

See also: [SELECT](Select), [HAVING](Having), [CUBE](Cube), [ROLLUP](Rollup), [GROUPING SETS](Grouping Sets)
