# REMOVE COLUMNS

Sometimes you may want to select all fields but without some of them. 

For example:
```js
    var data = [{a:1,b:10},{a:2,b:20}];
    var res = alasql('SELECT * REMOVE COLUMN b FROM ?',[data]);
    // returns [{a:!},{a:2}]
```

WIth [Angular.js](Angular.js) AlaSQL automatically remove ```$$hashKey``` (see [this example](http://jsfiddle.net/agershun/efmhcnu8/1/))


