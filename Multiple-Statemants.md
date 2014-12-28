## Single SQL statement

Returns a single value of query result:

* Query result
```
    alasql('SELECT * FROM one');
    [{a:1},{a:2}]
```

* Number of rows processed
```
    alasql('DELETE FROM one WHERE rownum < 363');
    362
```
* Number of database object processed (e.g. tables dropped):

```
    alasql('DROP DATABASE IF EXISTS geo');
    1 or 0
```
