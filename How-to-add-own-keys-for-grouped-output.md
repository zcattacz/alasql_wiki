# How to add own keys for grouped output?

Source: [StackOverflow.com](http://stackoverflow.com/questions/23600897/using-lodash-groupby-how-to-add-your-own-keys-for-grouped-output/27634449#27634449)

The raw data returned is this:
```js
    [
        {
            "name": "jim",
            "color": "blue",
            "age": "22"
        },
        {
            "name": "Sam",
            "color": "blue",
            "age": "33"
        },
        {
            "name": "eddie",
            "color": "green",
            "age": "77"
        }
    ]
```
I want the "group by" function to return an object that looks like this:
```js
    [
        {
            color: "blue",
            users: [
                {
                    "name": "jim",
                    "color": "blue",
                    "age": "22"
                },
                {
                    "name": "Sam",
                    "color": "blue",
                    "age": "33"
                }
            ]
        },
        {
            color: "green",
            users: [
                {
                    "name": "eddie",
                    "color": "green",
                    "age": "77"
                }
            ]
        }
    ]
```

### Answer
```js
    var res = alasql('SELECT color, ARRAY(_) AS users FROM ? GROUP BY color',[data]);
```
Try this example [in jsFiddle](ttp://jsfiddle.net/agershun/q40wrrk2/1/)