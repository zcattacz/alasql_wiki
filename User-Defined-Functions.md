# User-Defined Functions

```js
    alasql.fn.cube = function(x) { return x*x*x; }
    alasql(‘SELECT cube(x) FROM ?’,[data]);
```
  