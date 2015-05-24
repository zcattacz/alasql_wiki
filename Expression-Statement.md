# = Expression Statement

You can use expression statement strating with ```=```

Like:
```js
   alasql('= 2*2');
```
returns 4

And with internal subqueries:
```js
    alasql(' = (SELECT 2) * 2');
```
returns 4