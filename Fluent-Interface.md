# Fluent Interface

```js
    var res = alasql(data)
              .Where(function(x){x.Population>1000000})
              .OrderBy("Name")
              .exec();
```

## Supported functions
* Select()
* From()
* GroupBy()
* Having()
* OrderBy()
* Top()



