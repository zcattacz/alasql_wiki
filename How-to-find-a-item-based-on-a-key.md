# How to find a item based on a Key?

Source: [StackOverflow.com](http://stackoverflow.com/questions/5672788/given-a-json-object-how-to-find-a-item-based-on-a-key/27645245#27645245)

### Question

Given a JSON object like:
```js
    var data = {items: [
        {value: "21", name: "Mick Jagger"},
        {value: "43", name: "Johnny Storm"},
        {value: "46", name: "Richard Hatch"},
        {value: "54", name: "Kelly Slater"},
        {value: "55", name: "Rudy Hamilton"},
        {value: "79", name: "Michael Jordan"}
    ]};


How can I do something like this:
```js
    datagood = data.where(value == 55)
```

Is something like that possible with JS?

### Alasql

Alasql library can perform more complex queries with "old good" SQL:
```js
    var res = alasql('SELECT * FROM ? WHERE value = 55',[data]);
```
Try this example [in jsFiddle](http://jsfiddle.net/agershun/11gd86nx/1/)