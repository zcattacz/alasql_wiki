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



  

Also see [compiled statements](Compilation)