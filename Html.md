# Keyword `HTML`

AlaSQL can read data from a HTML table and store data into a HTML table. This only works in the browser. 

Syntax:
```sql
    SELECT column INTO HTML(cssSelector,options) FROM tableid;
    SELECT column FROM HTML(cssSelector,options) ;
```

### Data from HTML table

```js
    alasql('SELECT * FROM HTML("#MyTable", {headers:true})');
```


### Data into HTML table
```js
    alasql('SELECT * INTO HTML("#MyTable", {headers:true}) FROM ?',[data]);
```

See also: [CSV](Csv), [TAB](Tab), [TSV](Tsv), [XLSX](Xlsx), [JSON](Json)
