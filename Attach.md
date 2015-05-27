# ATTACH

Attach local or external database to AlaSQL.

Syntax:
```sql
    ATTACH [engineid] DATABASE databaseid [(parameters)];
```

Currently AlaSQL supports these database engines:
* [LOCALSTORAGE](LocalStorage)
* [INDEXEDDB](IndexedDB)
* [FILESTORAGE](FileStorage)

This statement can be used for attachment of external databases:
```js
    alasql('ATTACH LOCALSTORAGE DATABASE mybase');
```