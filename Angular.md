

### Angular.js + AlaSQL

You can use AlaSQL together with Angular.js framework:

```js
    $scope.exportData = function () {
        alasql('SELECT * INTO XLSX("john.xlsx",{headers:true}) FROM ?',[$scope.items]);
    };
```
See [simple example in jsFiddle](http://jsfiddle.net/agershun/00nfeq12/).

Other examples of AlaSQL and Angular.js integration: 

* [Calculating average of array](http://jsfiddle.net/agershun/she06Lq3/2/)