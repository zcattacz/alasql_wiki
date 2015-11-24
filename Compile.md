# Precompile SQL statements 

`alasql.compile()` lets you precompile statements. It is a kind a "prepare" in other SQL databases.

To compile statement use:

```js
   var stmt = alasql.compile(sql [, dbName])
```

Then run the statement:
```js
   stmt([parameters array] [, callback])
```

Compiled statement examples:

```js
    var bigSum = alasql.compile('SELECT SUM(a) FROM one WHERE a>?', 'myDBname'); // no DBname needed
    var foo = bigSum([10]) ;
```

```js
    var ins = alasql.compile('INSERT INTO one VALUES (?,?)'); // no DBname needed
    ins(1,10);
    ins(2,20);
```



Here is the example how to calculate sum of numbers > 2 from [1,2,3,4,5]:
```js
    var data = [{a:1},{a:2},{a:3},{a:4},{a:5}];

    // Compile
    var mysum = alasql.compile("SELECT VALUE SUM(a) FROM ? WHERE a > 2");

    // Run
    var res = mysum([data])
```

How to deal with parameters:
```
    var insert1 = db.compile('INSERT INTO one (?,?)');
    var insert2 = db.compile('INSERT INTO one ($a,$b)');
    var insert3 = db.compile('INSERT INTO one (:a,:b)');

    insert1([1,2]);
    insert2({a:1,b:2});
    insert3({a:3,b:4});
```
Try this example in [jsFiddle](http://jsfiddle.net/7cn8kp16/1/)