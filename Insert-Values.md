## INSERT VALUES

Syntax:
```sql
    INSERT INTO tableid VALUES (vaule,...), ...
    INSERT INTO tableid VALUES {key:value, ...}, ...
```
For example:
```js
    alasql('CREATE TABLE Cities (City STRING, Population NUMBER)');
    alasql('INSERT INTO Cities VALUES ("Moscow", 11500000), ("London",6000000)');
    alasql('INSERT INTO Cities VALUES ?',[{City:'Berlin', Population:4300000}]);
    alasql('INSERT INTO Cities VALUES (?,?)',["Beijing",5000000]);
    alasql('INSERT INTO Cities VALUES {City:"Paris",Population:5000000}');
```

See also: [INSERT](Insert)