# Keyword `MIN`

Minimal aggregator and function.

Syntax:
```sql
    MIN([DISTINCT] expression) -- aggregator
    MIN(expression1, expression2, ...) -- function
```

## Unclean data

'null' will be treated as `0` so if you have unclean data its suggested that you make your own aggregation with [[user defined functions]]:

```js
  alasql.aggr.LEAST = function(v,s,stage){
    if(stage == 1) return v;
    if(stage == 2) {
        if(v == null) return s;
        else return Math.min(s,v);;
    }
    return s; 
  };
var res = alasql('SELECT LEAST(a) FROM ?',[data])
```


----
See also: [MAX](Max), [LEAST](Least)
