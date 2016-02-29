# Keyword `CSV`

AlaSQL can import from and export to CSV (comma-separated values) format.

Syntax:
```sql
    SELECT column INTO CSV(filename,options) FROM tableid;
    SELECT column FROM CSV(filename,options) ;
```

Please note that when interacting with files AlaSQL [will run async](async). We strongly recommend you to [use the promise notation](promise).

### Import CSV data
```js
    alasql.promise('SELECT * FROM CSV("my.csv". {headers:true})')
            .then(function(data){
                 console.log(data);
            }).catch(function(err){
                 console.log('Error:', err);
            });
```
You can try this example [in jsFiddle](http://jsfiddle.net/agershun/efmhcnu8/1/)

You can specify delimiters and quote characters:
```js
    alasql.promise('SELECT * FROM CSV("my.csv". {headers:true, quote:"\'",separator:","})')
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
    alasql.promise('SELECT * INTO CSV("my.csv". {headers:true}) FROM ?',[data])
            .then(function(){
                 console.log('Data saved');
            }).catch(function(err){
                 console.log('Error:', err);
            });;
```
See also: [TAB](Tab), [TSV](Tsv), [XLSX](Xlsx), [JSON](Json)

