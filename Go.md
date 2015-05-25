# GO

In AlaSQL all stetements san be separated with ```;```(semicolon) or with ```GO``` keyword:
```sql
    SELECT * FROM one; SELECT * FROM two GO SELECT * FROM three
```

In case of multiline stetement ```alasql()``` stores all results into array with results:
```js
    var res = alasql('SELECT 10');
    // returns [{'10':10}]

    var res = alasql('SELECT 10 GO SELECT 20');
    // returns [ [{10:10}], [{20:20}] ]
```

