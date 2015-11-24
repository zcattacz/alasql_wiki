
Compiled statement examples:

```js
    var bigSum = alasql.compile('SELECT SUM(a) FROM one WHERE a>?', 'myDBname'); // no DBname needed
    var foo = bigSum([10]) ;
```

```js
    var ins = alasql.compile('INSERT INTO one VALUES (?,?)'); // no DBname needed
    ins(1,10);
    ins(2,20);
```

