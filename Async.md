# Async

Sync version:
```js
    var result = alasql(sql, params)
```

Async version:
```js
    alasql(sql, params, function(result) {
 	// do something with result
    });
```

It is impossible to use sync version with async operations like:
* IndexedDB functions
* INTO- and FROM-functions

This is the example:
```js
     var resSync = alasql('SELECT * FROM CSV("mydata.csv")')',[],function(resAsync){
          console.log(resAsync);
     });
     console.log(resSync);
```