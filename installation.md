

# How to use

For the browser: Include [alasql.min.js](http://cdn.jsdelivr.net/alasql/latest/alasql.min.js) and call 
`alasql()` with your SQL statements:

```html

<script src="//cdn.jsdelivr.net/alasql/0.1/alasql.min.js"></script> 

<script>
    
	alasql("CREATE TABLE cities (city string, population number)");
        
	alasql("INSERT INTO cities VALUES ('Rome',2863223), ('Paris',2249975), ('Berlin',3517424),  ('Madrid',3041579)");
        
	var res = alasql("SELECT * FROM cities WHERE population < 3500000 ORDER BY population DESC");
   
   // res now contains this array of object:
   // [{"city":"Madrid","population":3041579},{"city":"Rome","population":2863223},{"city":"Paris","population":2249975}] 	
   
</script>
```

Play with this example in [jsFiddle](http://jsfiddle.net/xxh13gLa/) 

----


### Bower

To use AlaSQL via bower install as normal

    bower install alasql --save

----

### Meteor

To use AlaSQL with Meteor install as normal

    meteor add agershun:alasql

----

### Node.js or IO.js


For node install with npm

```
npm install alasql --save
```


> [![NPM](https://nodei.co/npm/alasql.png)](https://nodei.co/npm/alasql/) [![NPM](https://nodei.co/npm-dl/alasql.png?months=6)](https://nodei.co/npm/alasql/)



Require `alasql` and create a new database to start executing your SQL.


```js
var alasql = require('alasql');

var db = new alasql.Database();

db.exec("CREATE TABLE example (a INT, b INT)");

// You can insert data directly from javascript object...
db.tables.example1.data = [ 
    {a:5,b:6},
    {a:3,b:4}
];

// ...or you can insert data with normal SQL 
db.exec("INSERT INTO example1 VALUES (1,3)");

var res = db.exec("SELECT * FROM example1 ORDER BY b DESC");

// res now contains this array of objects:
// [{a:1,b:3},{a:3,b:4},{a:3,b:4}]
```

----

### Commandline

You can access AlaSQL [from the comandline](https://github.com/agershun/alasql/wiki/Alacon) by installing from npm globally

```
npm install alasql -g
```

Now you can access `alasql` via the commandline

```
> alasql "SELECT * INTO json('my.json') from xlsx('cities.xlsx',{headers:true}) WHERE population > 20000000"
```

To get get value instead of a JSON you can prepend `VALUE` to the `SELECT`

`?` will be replaced with the corresponding n'th argument.

```
alacon "VALUE SELECT 20-?+?" 5 100
```

See more examples [at the wiki](https://github.com/agershun/alasql/wiki/Alacon) 





## Other options


### For debug

Copy following files from `dist` catalog to your project

* dist/alasql.js
* dist/alasql.js.map

Include file: alasql.js or to the HTML page:

```html
  <script src="alasql.js"></script>  
  <script>
    alasql("CREATE TABLE test (language INT, hello STRING)");
    alasql("INSERT INTO test VALUES (1,'Hello!')");
    alasql("INSERT INTO test VALUES (2,'Aloha!')");
    alasql("INSERT INTO test VALUES (3,'Bonjour!')");
    console.table(alasql("SELECT * FROM test WHERE language > 1"));
  </script>

```

### In browser with AMD or UMD

You can use alasql.js with define()/require() functions in browser as well, because it supports AMD and UMD:

```js
    require(['alasql.js'], function(alasql) {
        var test1 = [{a:1,b:2,c:3},{a:4,b:5,c:6},{a:7,b:8,c:9}];
        console.log( alasql('SELECT a, b*c AS bc FROM ? AS t',[test1]) );
    });
```
