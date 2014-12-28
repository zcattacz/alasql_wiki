# How to count matching values in array?

Source: [StackOverflow.com](http://stackoverflow.com/questions/2228362/how-to-count-matching-values-in-array-of-javascript/27659654#27659654)

### Question

What is a any good algorithm/code to get list of unique values from array and count of its occurrence in array?

### Answer
The example:
```js
    var data = [1,2,3,4,3,2,3,4,5,3,2,1,1,1,2];

    var res = alasql('SELECT INDEX _, COUNT(*) FROM ? GROUP BY _',[data]);
```
You can try this example [at jsFiddle](http://jsfiddle.net/agershun/L6qa4r94/1/);
