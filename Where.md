# SELECT WHERE

Expression
```js
    var res = alasql('SELECT * FROM City WHERE Population > 1000000');
```

## WHERE EXIST() / NOT EXIST()
```js
    var res = alasql('SELECT * FROM City WHERE \
            EXIST(SELECT * FROM Capital WHERE City.Name = Capital.Name)');
```