# Keyword `TRANSACTION`

The keyword TRANSACTION is optional

Begin
```js
    alasql('BEGIN');
    alasql('BEGIN TRANSACTION');
```
 
Commit
```js
    alasql('COMMIT');
    alasql('COMMIT TRANSACTION');
```

Rollback
```js
    alasql('ROLLBACK');
    alasql('ROLLBACK TRANSACTION');
```

#### Transaction realization
In version 0.0.35 AlaSQL supports transactions only for Local Storage and DOM-storage database. Full support for other databases will be available in future versions


See also: [COMMIT](Commit), [ROLLBACK](Rollback)