# Alasql JavaScript API

## Alasql object

*alasql* is a main object and function of Alasql library. It can be used in some different ways:  

```html
    <script src="alasql.js"></script>
    <script>
    	alasql('create table capitals (country string, city string, population int)');
    	alasql('insert into capitals values ("USA", "Washington, D.C.", 646449)');
    	alasql('insert into capitals values ("France", "Paris", 2211000)');
    	alasql('insert into capitals values ("Russia", "Moscow", 11500000)');
    	alasql('insert into capitals values ("Mexica", "Mexico City", 8851000)');
    	alasql.log('select city,population from capitals order by population desc');
    </string>
```

1. Execute SQL statement or set of statements:
```js
    alasql(sql-statement)
```

2. Class for a number functions:
* alasql.exec(sql, params, callback) - execute SQL statement
* alasql.value(sql, params, callback) - execute SQL statement but return only one value
* alasql.log(sql, params) - execute SQL statement and log the results to console or into HTML tag

3. Class for options:
* alasql.options.logtarget - target for alasql.log() functions. Values can be "console" or HTML tag
