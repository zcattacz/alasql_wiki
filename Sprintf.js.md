# Formatting with Sprintf.js

You can use standard [sprintf()](https://github.com/alexei/sprintf.js) function for format dates and numbers:
```js
    alasql.fn.sprintf = sprintf;
    var res = alasql('SELECT sprintf("%b",123)');
```

See full example [in jsFiddle](http://jsfiddle.net/agershun/5ssvje3k/).