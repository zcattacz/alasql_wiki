#ROWNUM() / ROW_NUMBER()

You can receive number of result record in the recordset like in this example:

```js
alasql('CREATE TABLE one (a INT PRIMARY KEY)');

for(var i=1;i<1000;i++) {
   alasql('INSERT INTO one VALUES (?)',[i]);
};

var res = alasql('SELECT * \
    FROM (SELECT a, ROWNUM() AS r FROM one)\
    WHERE r BETWEEN 55 AND 60');
```
You can try this example [in jsFiddle](http://jsfiddle.net/agershun/81noowmn/11/)