# DECLARE

AlaSQL allows to create local variables with ```@``` prefix:
```js
    var res = alasql('DECLARE @one char(3) = "abcdef"; SELECT VALUE @one')[1];
    // returns "abcdef"
```
Try this example in [jsFiddle](http://jsfiddle.net/agershun/g9jmt6hg/5/).
