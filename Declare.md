# DECLARE

Syntax:
```sql
    DECLARE variable type [= expression]
```

AlaSQL allows to create local variables with ```@``` prefix:
```js
    var res = alasql('DECLARE @one char(3) = "abcdef"; SELECT VALUE @one')[1];
    // returns "abcdef"
```
Try this example in [jsFiddle](http://jsfiddle.net/agershun/g9jmt6hg/5/).

### Extended syntax
You can assign value immediatly to the declared variable:
```sql
     DECLARE @var1 type1 = expr1, @var2 type2;
```

See also: [SET](Set)