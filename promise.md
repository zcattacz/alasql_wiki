# `Promise` notation

You can use `promise` notation for AlaSQL

```js
alasql.promise('SELECT * FROM XLS("mydata.xls") GROUP BY name WHERE lastname LIKE "A%" and city = "London"')
      .then(function(res){
           console.log(res);
      }).catch(function(err){
           console.log('error:', err);
      });
```

AlaSQL uses ES6 promises which are available in most modern browsers. If you need to support browsers that do not support Promises, fear not! There is a [polyfill](https://github.com/jakearchibald/es6-promise/blob/master/dist/es6-promise.min.js) for you to include.



