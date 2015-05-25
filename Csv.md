# CSV

AlaSQL can import export JavaScript arrays to CSV (comma-separated values) format.

### Import CSV data
```js
    alasql('SELECT * FROM CSV("my.csv". {headers:true})');
```
You can try this example [in jsFiddle](http://jsfiddle.net/agershun/efmhcnu8/1/)

You can specify delimiters and quote characters:
```js
    alasql('SELECT * FROM CSV("my.csv". {headers:true, quote:"\'",separator:","})');
```

### Export CSV data
```js
    alasql('SELECT * INTO CSV("my.csv". {headers:true}) FROM ?',[data]);
```
