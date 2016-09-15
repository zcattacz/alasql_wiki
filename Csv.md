# Keyword `CSV`

AlaSQL can import from and export to CSV (comma-separated values) format.

Syntax:
```sql
    SELECT column INTO CSV(filename,options) FROM tableid;
    SELECT column FROM CSV(filename,options) ;
```

Please note that when interacting with files AlaSQL [will run async](async). We strongly recommend you to [use the promise notation](promise) instead of the simple notation: [`alasql(sql, params, function(data) { console.log(data) })`](async)


### Import CSV data
```js
    alasql.promise('SELECT * FROM CSV("my.csv", {headers:false})')
            .then(function(data){
                 console.log(data);
            }).catch(function(err){
                 console.log('Error:', err);
            });
```
You can try this example [in jsFiddle](http://jsfiddle.net/agershun/efmhcnu8/1/)

You can also give the full content of a CSV file as a string instead of the path. 

You can specify delimiters and quote characters:
```js
    alasql.promise('SELECT * FROM CSV("my.csv", {headers:true, quote:"\'",separator:","})')
            .then(function(data){
                 console.log(data);
            }).catch(function(err){
                 console.log('Error:', err);
            });
```

Example on how to change the seperator only
```js
   alasql.promise('SELECT * FROM CSV("a.csv",{separator:";"})')
            .then(function(data){
                 console.log(data);
            }).catch(function(err){
                 console.log('Error:', err);
            });
```

### Export to CSV data
```js
    alasql.promise('SELECT * INTO CSV("my.csv", {headers:true}) FROM ?',[data])
            .then(function(){
                 console.log('Data saved');
            }).catch(function(err){
                 console.log('Error:', err);
            });;
```


## Options

For CVS you can set the following options

- **header** is default `true`. If set to `false` the first row in the CVS file will contain data instead of the column names
- **utf8Bom** default depends on header. If headers will be included it will be default `true`. If headers not included it will be default `false`. If `true` BOM will be added to the CSV file (useful in some cases with excel)
- **separator** is default `;` and can be set to any string used as a seperator
- **quote** is default `"` and can be set to any string used to quote strings


See also: [TAB](Tab), [TSV](Tsv), [XLSX](Xlsx), [JSON](Json)

