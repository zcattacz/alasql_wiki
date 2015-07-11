# Excel 2003 files: .XLS

AlaSQL can read and export data in Excel 2003 format (.xls) with coloring of cells.


```js
    var opts = {
      headers: true,
      sheetid: 'My Birds',
      style:"background:#00ff00",
      columns: [
        {columnid:'a',title:'Albatroses',
          style:'background:red;font-size:20px',
          cell:{style:'background:blue'}
        },
        {columnid:'b',title:'Bird',cell:{
          style:function(value,sheet,row,column,rowidx,columnidx){
            return 'background'+(value==10?'brown':'white')
        }}},
        { 
          columnid: 'b', cell:{value:function(value){ return value * value}}
        }
      ]
    };

    var res = alasql('SELECT * INTO XLS("restest257a.xls",?) FROM ?',[opts,data]); 

```
Please, see the example with advanced color syntax [in jsFiddle](http://jsfiddle.net/agershun/95j0txwx/2/).


If you need Excel 2007 files please check out [[XLSX]]