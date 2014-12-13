## TOP

```js
    var data = [];
    for(var i=0;i<100;i++) data.push({num:i});
    var res = alasql('SELECT TOP 10 * FROM ?',[data]);
```