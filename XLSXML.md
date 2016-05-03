AlaSQL has XLSXML() export function with coloring functionality:

```js
var data = [{city:"London",population:5000000}, 
    {city:"Moscow",population:12000000},
    {city:"Mexico",population:20000000}, 
    {city:"New York",population:20000000}, 
];

var opts = {
  headers:true, 
  column: {style:{Font:{Bold:"1"}}},
  rows: {1:{style:{Font:{Color:"#FF0077"}}}},
  cells: {1:{1:{
    style: {Font:{Color:"#00FFFF"}}
  }}}
};
alasql('SELECT * INTO XLSXML("restest280b.xlsx",?) FROM ?',[opts,data]);
```

Here you can define style for any column, row, or cell in the sheet.