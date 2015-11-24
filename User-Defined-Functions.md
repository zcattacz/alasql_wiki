# User defined functions

To define new functions for SQL simply add it to ```alasql.fn``` variable, like below:
```js
    alasql.fn.cube = function(x) { return x*x*x; }
    alasql(‘SELECT cube(x) FROM ?’,[data]);
```

You can use alasql inside alasql functions, like below:
```js
    alasql.fn.myfilter = function(phase) {
        return alasql('SELECT VALUE COUNT(*) FROM ? WHERE Phase = ?',[data,phase]) == 2;
    };

    var res = alasql('SELECT * FROM ? WHERE myfilter(Phase)',[data]);
```
See the working example [in jsFiddle](http://jsfiddle.net/agershun/1nccgs6n/3/)

## User-defined functions and [compiled statements](Compilation)

Custom functions:
```js
    alasql.fn.myfn = function(a,b) {
        return a*b+1;
    }
    var res = alasql('SELECT myfn(a,b) FROM one');
```


  