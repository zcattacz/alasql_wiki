# Presompile SQL statements 

`alasql.compile()` lets you precompile statements. It is a kind a "prepare" in other SQL databases.

To compile statement use:

```js
   var stmt = alasql.compile(sql)
```

Then run the statement:
```js
   stmt([parameters array] [, callback])
```

Here is the example how to calculate sum of numbers > 2 from [1,2,3,4,5]:
```js
    var data = [{a:1},{a:2},{a:3},{a:4},{a:5}];

    // Compile
    var mysum = alasql.compile("SELECT VALUE SUM(a) FROM ? WHERE a > 2");

    // Run
    var res = mysum([data])
```

Try this example in [jsFiddle](http://jsfiddle.net/7cn8kp16/1/)