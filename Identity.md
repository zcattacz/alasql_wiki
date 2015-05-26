# IDENTITY, AUTO_INCREMENT, AUTOINCREMENT

AlaSQL supports autoincrement feature:
```js
    alasql('CREATE TABLE one (a INT AUTO_INCREMENT, b STRING)');
    alasql('INSERT INTO one (b) VALUES ("one"), ("two")');
    var res = alasql('SELECT * FROM one');
    // returns [{"a":1,"b":"one"},{"a":2,"b":"two"}]
```

Try this example [in jsFiddle](http://jsfiddle.net/x6cht8z1/1/)

By default AlaSQL the initial value is 1 and th step is 1, but you can change it:
```js
    alasql('CREATE TABLE one (a INT IDENTITY(10,5), b STRING)');
```