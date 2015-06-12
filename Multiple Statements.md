# Multiple SQL statements 

##Single SQL statement

Returns a single value of query result:

* Query result
```js
    alasql('SELECT * FROM one');
    => [{a:1},{a:2}]
```

* Number of rows processed
```js
    alasql('DELETE FROM one WHERE rownum < 363');
    => 362
```
* Number of database object processed (e.g. tables dropped):

```js
    alasql('DROP DATABASE IF EXISTS geo');
    => 1 (if dropped) or 0 (if not exists)
```

## Multiple SQL statements

Return array of results in array, each element is a result for each statements processed:
```js
    alasql(“CREATE DATABASE test; USE test1”);
    => [1,0, [{a:1},{a:2}]]
```

In async call all statements run in sequence, one after previous statements finished.
