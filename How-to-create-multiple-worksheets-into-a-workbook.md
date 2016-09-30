# How to create multiple worksheets into a workbook?

This is how to prepare a single sheet of data.
```js
    var data = [];
    alasql('SELECT * INTO XLSX ("mydata.xlsx", { headers:true }) FROM ?', data);
```

To export multisheet workbook use this code:
```js
    var data1 = [{a:1,b:10},{a:2,b:20}];
    var data2 = [{a:100,b:10},{a:200,b:20}];
    var opts = [{sheetid:'One',header:true},{sheetid:'Two',header:false}];
    var res = alasql('SELECT INTO XLSX("restest344b.xlsx",?) FROM ?',[opts,[data1,data2]],
      function(){
        done();
      });
```
You can try this example [in jsFiddle](http://jsfiddle.net/6ckj281f/).

Please note, that by some reason AlaSQL uses this syntax ```SELECT FROM``` without star inside. This syntax is equvalent to ```SELECT COLUMN _ FROM```, that different from ```SELECT * FROM```, because second syntax creates new objects on the base of data. 

