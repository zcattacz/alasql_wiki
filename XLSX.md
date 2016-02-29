# `.XLSX` - Excel 2007 

AlaSQL can export data to Excel 2007 and LibreOffice format with colors and other Excel formatting functions. This also works in IE9. 

Please note that when interacting with files AlaSQL [will run async](async). We strongly recommend you to [use the promise notation](promise) instead of the simple notation: [`alasql(sql, params, function(data) { console.log(data) })`](async)


### Read from XLSX

```js
    alasql.promise('select City, Population from xlsx("cities.xlsx") where Population > 100000')
            .then(function(data){
                 console.log(data);
            }).catch(function(err){
                 console.log('Error:', err);
            });
```

### Save data to XLSX

```js

    alasql.promise('SELECT * INTO XLSXML("restest280b.xls") FROM ?', [data])
            .then(function(data){
                 console.log('Data saved');
            }).catch(function(err){
                 console.log('Error:', err);
            });
```
		
### Options

XLSX() function supports the following options:

#### sheetid
Sheet name:
```js
    alasql.promise('select * from xlsx("cities.xlsx",{sheetid:"Sheet2"}')
            .then(function(data){
                 console.log(data);
            }).catch(function(err){
                 console.log('Error:', err);
            });
```
By default AlaSQL read data from sheet "Sheet1".

#### Range
Cells range:
```js
    alasql.promise('select * from xlsx("cities.xlsx",{range:"A1:D100"}')
            .then(function(data){
                 console.log(data);
            }).catch(function(err){
                 console.log('Error:', err);
            });
```
By default AlaSQL read all data in the sheet.

#### headers
Read headers from data range (true/false):
```js
    alasql.promise('select * from xlsx("cities.xlsx",{headers:true}')
            .then(function(data){
                 console.log(data);
            }).catch(function(err){
                 console.log('Error:', err);
            });
```
By default AlaSQL headers are set to `true`


### Example

```js
    var mystyle = {
      headers:true, 
      column: {style:{Font:{Bold:"1"}}},
      rows: {1:{style:{Font:{Color:"#FF0077"}}}},
      cells: {1:{1:{
        style: {Font:{Color:"#00FFFF"}}
      }}}
    };
    alasql.promise('SELECT * INTO XLSXML("restest280b.xls",?) FROM ?',[mystyle,data])
            .then(function(data){
                 console.log('Data saved');
            }).catch(function(err){
                 console.log('Error:', err);
            });
```
See the working example in [jsFiddle](http://jsfiddle.net/95j0txwx/7/)

			

---

AlaSQL uses js-xlsx library to read and export Excel files.

js-xlsx at Github: https://github.com/SheetJS/js-xlsx

----

If you need Excel 2003 files please check out: [[XLS]]