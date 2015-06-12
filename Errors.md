# Error processing

AlaSQL worsk in two modes:
* with error trapping
* without error trapping

To turn error trapping on by setting `errorlog` to `true` in [`alasql.options`](alasql options)
```js
    alasql.options.errorlog = true; // Log or throw error
```


Now AlaSQL won't trow errors, but you can check for error codes in callback function, like here:
```js
    alasql.options.errorlog = true;
    alasql('SELECT 1/0',[],function(res,err) {
       console.log(err);
    });
```

### Error codes

The list of error codes is not yet ready.



See also: [ASSERT](Assert), [API](Api)

