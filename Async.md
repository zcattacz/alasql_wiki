# Async execution of SQL statements


Normal sync version would be
```js
    var result = alasql(sql, params)
```

To run Async version add a 3rd parameter as callback:
```js
	alasql(sql, params, function(result) {
		// do something with result
	});
```

AlaSQL will always run async in the following cases. 
* IndexedDB functions
* INTO- functions
* FROM-functions

Example:
```js
     var resSync = alasql('SELECT * FROM CSV("mydata.csv")')',[],function(resAsync){
          console.log(resAsync);
     });
     console.log(resSync);
```