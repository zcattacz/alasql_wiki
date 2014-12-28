# Transactions

Begin
```js
    alasql('BEGIN');
    alasql('BEGIN TRANSACTION');
```
 
Commit
```js
    alasql('COMMIT');
```

Rollback
```js
    alasql('ROLLBACK');
```

#### Transaction realization
In version 0.0.35 Alasql supports transactions only for Local Storage and DOM-storage database. Full support for other databases will be available in future versions
