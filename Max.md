# Keyword `MAX`

Maximal aggregator and function.

Syntax:
```sql
    MAX([DISTINCT] expression) -- aggregator
    MAX(expression1, expression2, ...) -- function
```


## Unclean data

'null' will be treated as `0` so if you have unclean data its suggested that you make your own aggregation with [[user defined functions]]:

```js
  alasql.aggr.MOST = function(v,s,stage){
    if(stage == 1) return v;
    if(stage == 2) {
        if(v == null) return s;
        else return Math.max(s,v);;
    }
    return s; 
  };
var res = alasql('SELECT MOST(a) FROM ?',[data])
```


----
See also: [MIN](Min), [GREATEST](Greatest)


