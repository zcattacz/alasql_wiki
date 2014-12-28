# How to intersect arrays of objects based on object property value?

Source: [StackOverflow.com](http://stackoverflow.com/questions/15441670/intersection-of-arrays-of-objects-based-on-object-property-value/27657487#27657487)

### Question
```js
    array1 = [ { id: "a", score: 1 }, { id: "b", score: 3 }, { id: "c", score: 8 }]
    array2 = [ { id: "a", score: 2 }, { id: "z", score: 5 }, { id: "c", score: 1 }]
    array3 = [ { id: "a", score: 3 }, { id: "f", score: 2 }, { id: "c", score: 2 }]
```
How can I get a result array containing only objects that have an id property value that exists and is the same in all arrays ? ie:
```js
    resultyArray = [ 
      { id: "a", score: 1 }, 
      { id: "a", score: 2 }, 
      { id: "a", score: 3 },
      { id: "c", score: 8 },
      { id: "c", score: 1 },
      { id: "c", score: 2 }
    ];
```

### Answer

You can do it with two function calls:
```js
    var res1 = alasql('SELECT id FROM ? \
             INTERSECT SELECT id FROM ? \
             INTERSECT SELECT id FROM ?',[array1,array2, array3]);

    var res2 = alasql('SELECT one.* FROM ? one \
             WHERE EXISTS(SELECT * FROM ? WHERE one.id = id) \
             ORDER BY id', 
             [array1.concat(array2).concat(array3), res1]);
```
Try this example [at jsFiddle](http://jsfiddle.net/ouwLtsz1/)