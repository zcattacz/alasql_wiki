#Google Spreadsheets

You an use Alasql with Tabletop library to read data from Goggle Spreadsheets:

First, add Alasql and Tabletop libraries to your page:
```html
    <script src="https://cdn.rawgit.com/jsoma/tabletop/master/src/tabletop.js"></script>
    <script src="http://alasql.org/console/alasql.min.js"></script>
    <div id="res"></div>
```

Second, publish spreadsheet file at Goggle Drive (in case of problem read this [StackoOverflow issue](http://stackoverflow.com/questions/28059346/get-json-feed-from-published-google-sheet)). Copy received access file key to the program.
```js
    var url='https://docs.google.com/spreadsheets/d/12VlQDuE1hgArpsJFBHlVbe4XN3CX5qwHvo-58ClMGzU/pubhtml';
```

Third, use TABLETOP from-function like in the example below:
```js
    alasql('SELECT * INTO HTML("#res",{headers:true}) FROM TABLETOP(?)',[url]);
```
