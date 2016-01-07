# Keyword `CSV`

AlaSQL can import from and export to CSV (comma-separated values) format.

Syntax:
```sql
    SELECT column INTO CSV(filename,options) FROM tableid;
    SELECT column FROM CSV(filename,options) ;
```

### Import CSV data
```js
    alasql('SELECT * FROM CSV("my.csv". {headers:true})');
```
You can try this example [in jsFiddle](http://jsfiddle.net/agershun/efmhcnu8/1/)

You can specify delimiters and quote characters:
```js
    alasql('SELECT * FROM CSV("my.csv". {headers:true, quote:"\'",separator:","})');

```

Example on how to change the seperator only
```js
   alasql('SELECT * FROM CSV("a.csv",{separator:";"})');
```

### Export CSV data
```js
    alasql('SELECT * INTO CSV("my.csv". {headers:true}) FROM ?',[data]);
```
See also: [TAB](Tab), [TSV](Tsv), [XLSX](Xlsx), [JSON](Json)

