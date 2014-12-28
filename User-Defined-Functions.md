# User-Defined Functions

```js
    alasql.fn.cube = function(x) { return x*x*x; }
    alasql(‘SELECT cube(x) FROM ?’,[data]);
```

## User-defined functions and compiled statements

Custom functions:
```js
    alasql.fn.myfn = function(a,b) {
        return a*b+1;
    }
    var res = alasql(‘SELECT myfn(a,b) FROM one’);
```

Compiled statements:
```js
    var ins = alasql.compile(‘INSERT INTO one VALUES (?,?)’);
    ins(1,10);
    ins(2,20);
```

Compiled functions:
```js
    var bigSum = alasql.compile(‘SELECT SUM(a) FROM one WHERE a>3’, ‘value’);
    var res = bigSum([10]) + 10;
```


  