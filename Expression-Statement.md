# Expression Statement (=)

In AlaSQL you can use expression statement starting with ```=```.

Syntax:
```sql
    = expression
```

For example:
```js
   alasql('= 2*2');
```
returns 4

And with internal subqueries:
```js
    alasql(' = (SELECT 2) * 2');
```
returns 4