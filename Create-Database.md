### Alasql Databases
To create Alasql 'native' database:
 
```js
    alasql('CREATE DATABASE mybase');
```

### External Databases
To create external (localStorage on IndexedDB) database:
```js
    alasql('CREATE LOCALSTORAGE DATABASE lsbase');
```
When you create external database, you need to [attach database](Attach) before usage:
```js
    alasql('CREATE INDEXEDDB DATABASE ixbase');
    alasql('ATTACH INDEXEDDB DATABASE ixbase AS myixdb');
```

### JavaScript Functions for Opening Databases

To create new database:

```js
	alasql('CREATE DATABASE [My Database]');

	// or

	new mydb = new alasql.Database();

	// or

	new mydb = new alasql.Database('My Database');
```

You can find database:

```js
	var mydb = alasql.Database('My Database');

	// or

	var mydb = alasql.databases['My Database'];
```