# Keyword `TABLETOP`

`TABLETOP` is used as a plugin to [read data from google spreadsheets](google-spreadsheets)

It takes one argument. The argument must be the URL to the html version of a published google spreadsheet.

There are 2 ways of providing the argument.

a) By giving the URL as parameter to AlaSQL with `?` in the TABLETOP funktion
```js
    var url='https://docs.google.com/spreadsheets/d/12VlQDuE1hgArpsJFBHlVbe4XN3CX5qwHvo-58ClMGzU/pubhtml';

    alasql('SELECT * INTO HTML("#res",{headers:true}) FROM TABLETOP(?)',[url]);
```

b) Place the value directly in the query string 
```js
    alasql('SELECT * FROM TABLETOP("https://docs.google.com/spreadsheets/d/12VlQDuE1hgArpsJFBHlVbe4XN3CX5qwHvo-58ClMGzU/pubhtml")');
```