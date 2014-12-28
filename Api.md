# Alasql JavaScript API

## SQL way
```js
    alasql(‘CREATE DATABASE test01’);
    alasql(‘USE test01’);
    alasql(‘CREATE TABLE one (a INT)’);
    alasql(‘INSERT INTO one VALUES (10)’):
    var res = alasql(‘SELECT * FROM one’);
```
## JavaScript way
```js
    var data = [{a:1}, {a:2}, {a:3}];
    alasql(‘SELECT * FROM ? WHERE a >= ?’, [data, 2]);

    // or
    var db = new alasql.Database();
    db.exec(“select * from one”, function(data) {
        console.log(data.length);
    });
```
## Alasql object
See [alasql object](Alasql Object)

## exec() function
WebSQL
```js
    var db = new alasql.Database(‘mydb’);
    db.exec(‘SELECT * FROM City”);
```

## JavaScript classes as SQL data types
```js
    alasql.fn.Date = Date;
    alasql(‘CREATE order (    orderno INT,    orderdate Date)’);
```

***NB.*** Classes are case-sensitive

## NEW (like JavaScript ‘new’ operator)

Register class as alasql type
```js
    alasql.fn.Date = Date;
```
Use NEW
```js
    alasql(‘SELECT NEW Date(yr,mn-1,dy) FROM orderdates’)
```

## JSON Objects
See [JSON Objects](Json Objects)

