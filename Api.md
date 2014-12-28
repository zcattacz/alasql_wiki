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

See [alasql object](Alasql Object)

