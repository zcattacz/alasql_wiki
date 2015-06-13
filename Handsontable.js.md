# SQL for Handsontable Grid

AlaSQL can be used as an SQL engine for [Handsontable grid](http://handsontable.com):

```js
    var hot = new Handsontable(document.getElementById('example'), {
        data: alasql('SELECT MATRIX * FROM ? ORDER BY [5]',[data]),
        colHeaders:     ["Year", "Maserati", "Mazda", "Mercedes", "Mini", "Mitsubishi"],
    });
```

See the example [in jsFiddle](http://jsfiddle.net/agershun/4wy9b7fd/).

