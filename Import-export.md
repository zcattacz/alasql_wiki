# Import and Export

## Export

You can save tables directly to the [CSV](Csv) file, like:
```js
    var data = [{a:1,b:10},{a:2,b:20}];
    alasql('select * into csv("a.csv",{headers:true}) from ?',[data]);
```

AlaSQL also supports [CSV](Csv), [TAB](Tsv) (or [TSV](Tsv)), [XLSX](Xlsx), [JSON](Json) formats.
