# Async execution of SQL statements

Using alasql will normally be sync
```js
    var result = alasql(sql[, params])
```

However, AlaSQL will always run async in the following cases. 
* IndexedDB functions
* INTO-functions (for example `SELECT * INTO CSV(...)`)
* FROM-functions  (for example `SELECT * FROM CSV(...)`)

We strongly recommend using the [[promise]] notation:

```js
alasql.promise('SELECT * FROM CLS("foo.csv")')
      .then(function(data){
           console.log(data);
      }).catch(function(err){
           console.log('Error:', err);
      });
```

If you feel very confident that you do not need to handle errors you can run async by add a 3rd parameter to alasql with a callback function:
```js
	alasql(sql, params, function(data) {
		// do something with data
	});
```
Note that if you have no params the value must be set to `[]`

Example:
```js
     var resSync = alasql('SELECT * FROM CSV("mydata.csv")',[],function(data){
          console.log(data);
     });
```

