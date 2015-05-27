# Error processing

AlaSQL work in two modes:
* with error trapping
* without error trapping

To turn on error trapping mode you can assign ```true``` to ```errorlog``` option:
```js
    alasql.options.errorlog = true; // Log or throw error
```

After that, AlaSQL won't trows error, but you can check for error codes in callback function, like here:
```js
    alasql.options.errorlog = true;
    alasql('SELECT 1/0',[],function(res,err) {
       console.log(err);
    });
```

### Error codes

The list of error codes is not yet ready.

See also: [ASSERT](Assert), [API](Api)

