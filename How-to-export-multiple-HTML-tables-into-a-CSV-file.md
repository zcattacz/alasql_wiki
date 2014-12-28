# How to export multiple HTML tables into a CSV file?

Source: [StackOverflow.com](http://stackoverflow.com/questions/22047174/how-do-i-export-multiple-html-tables-into-a-csv-file-using-javascript/27665054#27665054)

### Question

There are multiple tables that I want to export into a single CSV file. How could I do it?

### Answer

You can export table from multiple HTML tables to CSV (and XLSX file) with Alasql library.

See the working example below or try it [in jsFiddle](http://jsfiddle.net/agershun/97rp0r2g/):
```js
    function exportCSV() {
        var data1 = alasql('SELECT * FROM HTML("#table1",{headers:true})');
        var data2 = alasql('SELECT * FROM HTML("#table2",{headers:true})');
        var data = data1.concat(data2);
        alasql('SELECT * INTO CSV("data.csv",{headers:true}) FROM ?', [data]);
    }
```

```html
    <script src="http://alasql.org/console/alasql.min.js"></script>
    <button onclick="exportCSV()">Export table to Excel</button>
    <table width="100%">
    <tr><th>Table 1</th><th>Table 2</th>
    <tr><td>
    <table  id="table1" border="1"  align="center" >
        <thead>
             <tr><th>ID</th><th >Name</th><th>Month</th><th>Savings</th></tr>
        </thead>
        <tbody>
             <tr><td>101</td><td>John</td><td>January</td><td>$100</td></tr>
             <tr><td>102</td><td>Rianna</td><td>Feb</td><td>$200</td></tr>
             <tr><td>103</td><td>Michael</td><td>Mar</td><td>$300</td></tr>
       </tbody>
    </table>
    <td>
      <table  id="table2" border="1" align="center" >
         <thead>
             <tr><th>ID</th><th >Name</th><th>Month</th><th>Savings</th></tr>
        </thead>
        <tbody>
             <tr><td>101</td><td>Valentin</td><td>January</td><td>$10000</td></tr>
             <tr><td>102</td><td>Olga</td><td>Feb</td><td>$20000</td></tr>
             <tr><td>103</td><td>Alesya</td><td>Mar</td><td>$300000</td></tr>
       </tbody>
      </table>
   </table>
```
