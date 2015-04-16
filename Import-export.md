# Import and Export

### Export

You can save tables directly to the [CSV](Csv) file, like:
```js
    var data = [{a:1,b:10},{a:2,b:20}];
    alasql('select * into csv("a.csv",{headers:true}) from ?',[data]);
```
Try this example [in jsFiddle](http://jsfiddle.net/agershun/81noowmn/8/).

AlaSQL also supports export to [CSV](Csv), [TAB](Tsv) (or [TSV](Tsv)), [XLSX](Xlsx), and [JSON](Json) formats.

### Import

You can read tables directly from the [CSV](Csv) file, like:
```js
    var res = alasql('SELECT * FROM CSV("a.csv",{headers:true})');
```
