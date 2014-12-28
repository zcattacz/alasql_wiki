## Installation

### In browser

For production: copy file from ```dist``` catalog to your project

* dist/alasql.min.js

For debug: copy two files to your porject: 

* dist/alasql.js
* dist/alasql.js.map

Include file: alasql.js or alasql.min.js to the HTML page:

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

### In Node.js

Use the following command for installation:
```
    npm install alasql
```
Then require alasql.js module:

```js
    var alasql = require('alasql');

    var db = new alasql.Database();
    
    db.exec("CREATE TABLE test (one INT, two INT)");
    db.tables.test.data = [   // You can mix SQL and JavaScript
        {one:3,two:4},
        {one:5,two:6},
    ];
    var res = db.exec("SELECT * FROM test ORDER BY two DESC");
    console.log(res[0].one);

```
