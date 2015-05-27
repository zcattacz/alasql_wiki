# Highcharts.js with SQL

You can use AlaSQL to load and prepare data for Highcharts.js library.

Source: [Stackoverflow.com](http://stackoverflow.com/questions/27978027/preprocess-highchart-data-using-csv-file/27980656#27980656)

### Question

How to load CSV file from desktop and use it in Highcharts?

### Answer

You can add the following code to your page:
```html
    <script src="http://alasql.org/console/alasql.min.js"></script> 
    <input id="readfile" type="file" onchange="loadFile(event)"/>
    <script>
        function loadFile(event) {
            alasql('SELECT * FROM FILE(?,{headers:true})', [event],function(data){
                 // Process your data
            });
        );
    </script>
```

See the working example [in the code snippet](http://stackoverflow.com/a/27980656/3320509).
