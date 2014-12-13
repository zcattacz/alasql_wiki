You can load and save data in Microsoft Excel formats:

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
    alasql('select * from xlsx("cities.xlsx',{sheetid:"Sheet2"}',
        [],function(data){});
```
By default Alasql read data from sheet "Sheet1".

#### range
Cells range:
```js
    alasql('select * from xlsx("cities.xlsx',{range:"A1:D100"}',
        [],function(data){});
```
By default Alasql read all data in the sheet.

#### headers
Read headers from data range (true/false):
```js
    alasql('select * from xlsx("cities.xlsx',{headers:true}',
        [],function(data){});
```
By default Alasql headers are on.
