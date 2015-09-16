# Angular.js + AlaSQL


You can use AlaSQL together with Angular.js framework. Please include the file normally and not via requireJS. Please include alasql before requireJS to avoid issue of "Mismatched anonymous define() module". This issue is with requireJS.

```js
    $scope.exportData = function () {
        alasql('SELECT * INTO XLSX("john.xlsx",{headers:true}) FROM ?',[$scope.items]);
    };
```
See [simple example in jsFiddle](http://jsfiddle.net/agershun/00nfeq12/).

Another example: [Calculating average of array](http://jsfiddle.net/agershun/she06Lq3/2/)


## In more detail

If AlaSQL recognize Angular.js it removes ```$$hashKey``` artefacts from the exporting arrays.

To remove other artefact fields you can use [REMOVE COLUMNS](Remove Columns) clause.

(Source: [AlaSQL Group](https://groups.google.com/forum/?utm_medium=email&utm_source=footer#!msg/alasql/w9uavEdVHAU/k4KXf2Pv3WoJ) by **Built with AngularJS Application**)

For example, you can integrate these libraries it for import or export data files from MS Excel.

### Export file to Excel 
HTML:
```html
    <button ng-if="$root.appInfo.model.rows"     // show excel icon only if there are rows in the grid 
        class="btn"ng-click="$root.exportData()">
    </button> 
```
Controller:
```
    $rootScope.exportData = function () {
        alasql('SELECT * INTO XLSX("list.xlsx",{headers:true}) FROM ?', 
              [$rootScope.appInfo.model.rows]);   
    };
```

### Import data from file in client computer

Unfortunately, we cannot use ```ng-change``` because the input needs to be bound (```ng-model```), but it seems that ```type=file``` inputs are not supported for binding in Angular.js, so we can switch to ```ng-mouseleave``` and it worked, though we had to check in the function that a file had been chosen.

HTML:
```html
    <input type="file" ng-mouseleave="loadFile($event)" />
```
Controller:
```
    $rootScope.loadFile = function ($event) {
        if (event.fromElement.files.length==0) {
            return(false);   // leave in case no file was chosen
        };
        alasql('SELECT * FROM FILE(?,{headers:true})', [event], function (data) {
            $rootScope.eData = data;     //  eData contains the JSON representation of the Excel sheet rows
        }); 
    };
```
