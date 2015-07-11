# Standard Plug-ins

AlaSQL supports plugins but the feature is not yet documented.

Currently AlaSQL has one official plugins:
* [ECHO](https://github.com/agershun/alasql/blob/master/dist/alasql-echo.js) (working demo)

include plugins directly:

```html
    <script src="alasql.min.js"></script>
    <script src="alasql-echo.js"></script>
```

And `REQUIRE` the plugin

```js
    alasql('REQUIRE ECHO');
    var res = alasql('ECHO 123');  // logs 123 to the console
```


