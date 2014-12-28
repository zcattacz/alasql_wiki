# How to unique by multiple properties?

Source: [StackOverflow.com](http://stackoverflow.com/questions/26306415/underscore-lodash-unique-by-multiple-properties/27634393#27634393)

### Question

There is an array of objects with duplicates and I'm trying to get a unique listing, where uniqueness is defined by a subset of the properties of the object. For example,
```js
    {a:"1",b:"1",c:"2"}
```
And I want to ignore `c` in the uniqueness comparison.

### Answer
```js
    var data = [{a:"1",b:"1",c:"2"},{a:"1",b:"1",c:"1"}];

    var res = alasql('SELECT a,b FROM ? GROUP BY a,b',[data]);
```
Try this example [at jsFiddle](http://jsfiddle.net/agershun/L1g6vgLj/1/)