# Keyword `CALL

This statements allows to call procedures from SQL program.

Syntax:
```sql
    CALL procedure(arguments...)
```

For example:
```js
    alasql.fn.log = function(s) {
        console.log(s);
    } 
    alasql('CALL log(10)');
```