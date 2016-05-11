# Async execution of SQL statements

Using alasql will normally be sync
```js
    var result = alasql(sql [, params])
```

However, AlaSQL will always run async in the following cases. 

* INTO-functions (for example `SELECT * INTO CSV(...)`)
* FROM-functions  (for example `SELECT * FROM CSV(...)`)
* If using AlaSQL as a [[WebWorker]]
* All operations involving [[IndexedDB]]

If you are not sure what the point of async is, have a look at http://rowanmanning.com/posts/javascript-for-beginners-async and continue when you can explain the output order of A, B and C in http://jsfiddle.net/5Lnsxhf2/

## Promise notation
We strongly recommend using the [[promise]] notation:

```js
alasql.promise(sql [, params])
      .then(function(data){
           console.log(data);
      }).catch(function(err){
           console.log('Error:', err);
      });
```

### Chain of promises

If you put more than one SQL commands in the same string they will (until its fixed) run sync within in the async call to `alasql` - so a command like `"INSERT ...; SELECT * ..."` might not give the expected result as the select might run before the insert is done. 

You are able to pass an array of queries to `alasql.promise` and they will execute in a chain (so one after the return of the promise of the other). From version 0.2.7 the value passed to `.then` will be an array with the response of each of the queries. Pre 0.2.7 versions will only give the result from the last query executed. 

```js
alasql.promise([
	'CREATE FILESTORAGE DATABASE test123("./testDBfile.json")', 
	'ATTACH FILESTORAGE DATABASE test123("./testDBfile.json")', 
	'USE test123', 
	'CREATE TABLE IF NOT EXISTS products (id INT, category_id INT, name string, created_at DATE)', 
	['INSERT INTO products (id, category_id, name, created_at) VALUES (?,?,?,?)', [1, 2, 'XYZ', new Date()] ],
	'SELECT * FROM products'	
]).then(function(res){
	console.log('Result from last query:',res.pop())
}).catch(function(reason){
	console.log('Error:',reason)
})
```

Please note that to be able to combine a query with parameters instead of a string one must pass an array with the query string at index 0 and the array of parameters at index 1.


## Simple notation
Another way to execute code async is the simple notation
```js
	alasql(sql, [params,] function(data) {
		// do something with data
	});
```
Note that if you have no params the value is not needed

Example:
```js
     var resSync = alasql('SELECT * FROM CSV("mydata.csv")', function(data){
          console.log(data);
     });
```

For the simple notation you can ask for the second parameter to be an error
```js
alasql.options.errorlog = true; 
alasql('ATTACH INDEXEDDB DATABASE NN'.[].function(data,err){
    if(err) // do something with error;
});

```

Or you can handle errors in one central function for all executions

```js
alasql.options.errorlog = function(err){console.log(err)}; // Do something with error

alasql('ATTACH INDEXEDDB DATABASE NN'.[].function(data){
    //do something with data
});
```

Please note that the `.promise` notation is recommended.
