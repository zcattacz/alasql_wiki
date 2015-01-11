# Formatting Numbers with Numeral.js

You can use [Numeral.js](http://numeraljs.com/) library to format numbers in Alasql expressions:

```js
    var data = [{a:120000003.456},{a:567234.12}];
    // Pass numeral() function into alasql
    alasql.fn.numeral = numeral;
    // Use numeral() function
    alasql('SELECT numeral(a)->format("0,0") FROM ?',[data]);
```

See the example in jsFiddle](http://jsfiddle.net/agershun/drvga85x/1/).
