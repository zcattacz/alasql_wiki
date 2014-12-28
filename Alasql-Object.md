# Alasql Object
## Properties and functions

* alasql(sql,params,callback) – execute SQL
* alasql(data) - starting poit for [fluent interface](Fluent Interface)
* alasql.exec(sql,params,callback) – execute SQL
* alasql.parse(sql) – parse to [AST (abstract syntax tree)](AST)
* ast.compile(databaseid) – compile statement and cache it in database cache
* alasql.exec(sql) – execute statement
* alasql.use(databaseid) – [use database](Use Database)
* alasql.pretty(sql) – pretty SQL output in HTML and TXT
* alasql.options - options

## alasql() - main function
```js
    alasql(sql,[params],[callback])
```

**sql** – one or some SQL-statements separated by ‘;’
If one statement – alasql() returns one value
```sql
    USE test12 => 1
    SELECT * FROM one => [{a:1}, {a:2}]
```

If some statements – alasql() returns array of values, one for each statement
```sql
    USE test12; SELECT * FROM one => [1,[{a:1}, {a:2}]]
```

**params** – an array of parameters of SQL statement
You can use ? in SQL statement
```js
    alasql(‘SELECT a FROM ? WHERE b = ?’,[[{a:1,b:1}, {a:2,b:2}],2])
```
**callback** – a callback function
* Without callback alasql() runs synchroniously
* With callback alasql() runs asynchroniously with callbacks

See [Sync and Async](Async).

## How to use alasql()

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
