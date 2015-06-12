# Keyword `ATTACH`

Attach local or external database to AlaSQL.

Syntax:
```sql
ATTACH engineid DATABASE databaseid [(parameter,...)] [AS alias] 
```


Currently AlaSQL supports the following databaseid's:
* [LOCALSTORAGE](LocalStorage)
* [INDEXEDDB](IndexedDB)
* [FILESTORAGE](FileStorage)

Example:
```js
    alasql('ATTACH LOCALSTORAGE DATABASE mybase');
```


See also: [DETACH](Detach), [USE](Use)
