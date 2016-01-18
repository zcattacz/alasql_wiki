# `.XLSX` - Excel 2007 

AlaSQL can export data to Excel 2007 and LibreOffice format with colors and other Excel formatting functions. This also works in IE9. Code sample:

```js
    var mystyle = {
      headers:true, 
      column: {style:{Font:{Bold:"1"}}},
      rows: {1:{style:{Font:{Color:"#FF0077"}}}},
      cells: {1:{1:{
        style: {Font:{Color:"#00FFFF"}}
      }}}
    };
    alasql('SELECT * INTO XLSXML("restest280b.xls",?) FROM ?',[mystyle,data]);
```
See the working example in [jsFiddle](http://jsfiddle.net/95j0txwx/7/)



Another simple example:

```js
    alasql('select City, Population from xlsx("cities.xlsx") where Population > 100000',
       [], function(data){
       console.lod(data);
    });
```

### Options

XLSX() function supports the following options:

#### sheetid
Sheet name:
```js
    alasql('select * from xlsx("cities.xlsx",{sheetid:"Sheet2"}',
        [],function(data){});
```
By default AlaSQL read data from sheet "Sheet1".

#### Range
Cells range:
```js
    alasql('select * from xlsx("cities.xlsx",{range:"A1:D100"}',
        [],function(data){});
```
By default AlaSQL read all data in the sheet.

#### headers
Read headers from data range (true/false):
```js
    alasql('select * from xlsx("cities.xlsx",{headers:true}',
        [],function(data){});
```
By default AlaSQL headers are set to `true`



---

AlaSQL uses js-xlsx library to read and export Excel files.

js-xlsx at Github: https://github.com/SheetJS/js-xlsx

----

If you need Excel 2003 files please check out: [[XLS]]