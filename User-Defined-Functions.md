# User defined functions

To define new functions for SQL simply add it to ```alasql.fn``` variable, like below:


```js
    alasql.fn.cube = function(x) { return x*x*x; }
    alasql(‘SELECT cube(x) FROM ?’,[data]);
```

```js
    alasql.fn.double = function(x){return x*2};        
    alasql.fn.sum10 = function(x,y) { return x+y*10; }
    alasql('SELECT a, double(a) AS b, sum10(a,b) FROM test1');
```




You can use alasql inside alasql functions, like below:
```js
    alasql.fn.myfilter = function(phase) {
        return alasql('SELECT VALUE COUNT(*) FROM ? WHERE Phase = ?',[data,phase]) == 2;
    };

    var res = alasql('SELECT * FROM ? WHERE myfilter(Phase)',[data]);
```
See the working example [in jsFiddle](http://jsfiddle.net/agershun/1nccgs6n/3/)


## Aggregators

To make your own user defined aggregators please follow this example:

```js
alasql.aggr.MYAGGR = function (value, accumulator, stage) {
   if(stage == 1) {
       // first call of aggregator - for first line
       var newAccumulator =  value;
       return newAccumulator;
  } else if(stage == 2) {
     // for every line in the group
     accumulator = accumulator + value;
     return accumulator;
  } else {if stage == 3) {
     // Post production
     return accunulator;  
 }
}
```

See more examples here:
* [50functions.js](https://github.com/agershun/alasql/blob/develop/src/55functions.js#L230-L339)
* [test266.js](https://github.com/agershun/alasql/blob/develop/test/test266.js)

  

