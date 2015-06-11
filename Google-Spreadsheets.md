# Google Spreadsheets + AlaSQL

AlaSQL can query data directly from a google spreadsheet - so its easy to edit the raw data in the spreadsheet and make manipulations like grouping, filtering, or saving to XLSX directly in your app. The feature depends on the plugin [Tabletop library](https://github.com/jsoma/tabletop).

```html
<script src='https://cdn.rawgit.com/jsoma/tabletop/master/src/tabletop.js'></script>
<script src="//cdn.jsdelivr.net/alasql/0.1/alasql.min.js"></script> 

<div id="res"></div>

<script>
    var url = 'https://docs.google.com/spreadsheet/pub?hl=en_US&hl=en_US&key=0AmYzu_s7QHsmdDNZUzRlYldnWTZCLXdrMXlYQzVxSFE&output=html';

    alasql('SELECT * INTO HTML("#res",{headers:true}) FROM TABLETOP(?) WHERE name < "D" ORDER BY category',[url]);
</script>
```

Play with this example [in jsFiddle](http://jsfiddle.net/tov0zcmd/)

Remember to publish your spreadsheet. In case of problem read this [StackoOverflow question](http://stackoverflow.com/questions/28059346/get-json-feed-from-published-google-sheet). 

More info about [the `TABLETOP` keyword](TABLETOP)
