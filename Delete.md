## DELETE

Syntax:
```sql
    DELETE FROM table [WHERE expression]
```

Samples:
```js
    alasql('DELETE FROM cities WHERE population < 100000');
    alasql('DELETE FROM star WHERE name LIKE "A%"');
    alasql('DELETE FROM countries');
```

To delete all records from table:
```js
	alasql('DELETE FROM [Table A]');
```

To delete only selected records from table:
```js
	var numberOfDeletedLines = alasql('DELETE FROM [Table A] WHERE field1 > 10');
```

See also: [INSERT](Insert), [UPDATE](Update)