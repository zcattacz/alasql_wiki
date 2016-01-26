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


Please make sure `promise` is supported - for example by including [es6-promise](https://github.com/jakearchibald/es6-promise/blob/master/dist/es6-promise.min.js) - if using alasql in the browser. 




