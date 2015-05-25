# How to search deep nested JSON?

Source: [StackOverflow] (http://stackoverflow.com/questions/30091572/search-deep-nested-json)

### Question
<blockquote>
I am working on a solution where I need to search for an element in a deeply nested JSON by its id. I have been advised to use underscore.js which I am pretty new to.

After reading the documentation http://underscorejs.org/#find , I tried to implement the solution using find, filter and findWhere.

The issue I faced is that these functions check the top level of the JSON and not the nested properties thus returning undefined. I tried to use item.catalog && item.catalog.uid == 1; logic as suggested in a similar question Underscore.js - filtering in a nested Json but failed.

How can I find an item by value by searching the whole deeply nested JSON?
</blockquote>
```js
var test = {
    "menuInputRequestId": 1,
    "catalog":[
      {
        "uid": 1,
        "name": "Pizza",
        "desc": "Italian cuisine",
        "products": [
          {
            "uid": 3,
            "name": "Devilled chicken",
            "desc": "chicken pizza",
          },
          // ...
        ]
      }
    ]
  };
```

### Answer
You can do it with AlaSQL [SEARCH](Search) statement:
```js
     var res = alasql('SEARCH / * WHERE(uid=1) name FROM ?',[data]);
```

