# How to export JavaScript array info to CSV on client side?

### Question

There are the attribute info in array, which looks like this:
```js
    [["name1", "city_name1", ...]["name2", "city_name2", ...]]
```
Any idea how I can export this to csv on the client side?

### Answer

You can use [Alasql.js][1]library to export data locally in CSV (and XLSX as well) file format.

Below you can see a simple working example how to export data to CSV format.

```html
    <script src="http://alasql.org/console/alasql.min.js"></script>

    <button onclick="exportData()">Export data to CSV file</button>
```
```js
    var data = [["Minsk",100000], ["Riga",200000]];

    function exportData() {
        alasql("SELECT * INTO CSV('cities.csv') FROM ?",[data]);
    }
```
You can try this example [at jsFiddle](http://jsfiddle.net/agershun/g855dn9b/).


<!-- end snippet -->

