# How to aggregate an array of objects based on object property?

Source: [StackOverflow.com](http://stackoverflow.com/questions/15441272/in-an-array-of-objects-how-can-i-aggregate-based-on-object-property/27657206#27657206)

### Question
There is the following array of objects:
```js
    dataArray = [ 
      { id: "a", score: 1 }, 
      { id: "b", score: 2 }, 
      { id: "c", score: 5 }, 
      ...
      { id: "a", score: 3 },
      ...
      { id: "c", score: 2},
      ...
     ]
```
How can I obtain a resultArray like the following:
```js
    resultArray = [
      { id: "a", score: sum of all the scores when id is a },
      { id: "b", score: sum of all the scores when id is b },
      ...
      ...
    ]
```

### Answer

You can do it in one line with Alasql library. See the example [in jsFiddle](http://jsfiddle.net/agershun/k4hkbm53/1/).
```js
        var dataArray = [ { id: "a", score: 1 }, { id: "b", score: 2 }, { id: "c", score: 5 },
                          { id: "a", score: 3 }, { id: "c", score: 2}, ];

        var res = alasql('SELECT id, SUM(score) AS score FROM ? GROUP BY id',[dataArray ]);
```
