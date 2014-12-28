# How to group and sort a JS array?

Source: [StackOverflow.com](http://stackoverflow.com/questions/16164078/grouped-sorting-on-a-js-array/27595866#27595866)

### Question

There is an array of objects with two properties: Name and Hours.

For example:
```js
    array = [
        {name: "ANDY", hours: 40 }, 
        {name: "ANDY", hours: 50 }, 
        {name: "GREG", hours: 40 },
    ];
```
For example I would like the result of the sorting to have the Andy with the most hours first, then Andy with slightly less hours, and then Greg because his name comes later alphabetically and so on and so on.

### Answer

```js
    var res = alasql('SELECT * FROM ? ORDER BY Name, Hours DESC',[array]);
```
Try this example [at jsFiddle](http://jsfiddle.net/agershun/3v1fhybe/2/)
