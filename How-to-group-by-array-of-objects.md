# How to group by array of objects?

Source: [StackOverflow.com](http://stackoverflow.com/questions/14446511/what-is-the-most-efficient-method-to-groupby-on-a-javascript-array-of-objects/27617207#27617207)

### Question

What is the most efficient way to group by objects in an array? For example, given this array of objects:
```js
    [ 
        { Phase: "Phase 1", Step: "Step 1", Task: "Task 1", Value: "5" },
        { Phase: "Phase 1", Step: "Step 1", Task: "Task 2", Value: "10" },
        { Phase: "Phase 1", Step: "Step 2", Task: "Task 1", Value: "15" },
        { Phase: "Phase 1", Step: "Step 2", Task: "Task 2", Value: "20" },
        { Phase: "Phase 2", Step: "Step 1", Task: "Task 1", Value: "25" },
        { Phase: "Phase 2", Step: "Step 1", Task: "Task 2", Value: "30" },
        { Phase: "Phase 2", Step: "Step 2", Task: "Task 1", Value: "35" },
        { Phase: "Phase 2", Step: "Step 2", Task: "Task 2", Value: "40" }
    ]
```
I'd like to groupby different methods, but I want to sum the values.
```js
    [
        { Phase: "Phase 1", Value: 50 },
        { Phase: "Phase 2", Value: 130 }
    ]
```
And if I did groupy Phase / Step, I'd receive:
```js
    [
        { Phase: "Phase 1", Step: "Step 1", Value: 15 },
        { Phase: "Phase 1", Step: "Step 2", Value: 35 },
        { Phase: "Phase 2", Step: "Step 1", Value: 55 },
        { Phase: "Phase 2", Step: "Step 2", Value: 75 }
    ]
```

### Answer

You can do it with this code:
```js
    var data = [ { Phase: "Phase 1", Step: "Step 1", Task: "Task 1", Value: "5" },
                 { Phase: "Phase 1", Step: "Step 1", Task: "Task 2", Value: "10" }];

    var res = alasql('SELECT Phase, Step, SUM(CAST([Value] AS INT)) AS [Value] \
                      FROM ? GROUP BY Phase, Step',[data]);
```
Try this example [at jsFiddle](http://jsfiddle.net/agershun/ztc32a8h/1/).

***BTW:*** On large arrays (100000 records and more) AlaSQL faster tham Linq. See test [at jsPref](http://jsperf.com/alasql-vs-linq-on-groupby). 

Comments:

* Here I put Value in square brackets, because VALUE is a keyword in SQL
* I have to use CAST() function to convert string Values to number type.
