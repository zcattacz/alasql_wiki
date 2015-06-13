# About AlaSQL

AlaSQL is a JavaScript SQL database library designed for:

* JavaScript [data manipulation](Data manipulation) and advanced filtering, grouping and joining
* Client-side [SQL database](Sql database) with persistence
* Fast data processing for BI and ERP applications
* Easy [ETL](Etl) (extract, transfer, and loading) data in [CSV](Csv), [XLSX](Xlsx), and other formats
* It works in all major browsers,  Node.js, and mobile applications

## Information about AlaSQL
* GitHub - [http://github.com/agershun/alasql](http://github.com/agershun/alasql)
* Official site - [http://alasql.org](http://alasql.org)

## JavaScript SQL
* [Other JavaScript SQL databases](Similar-Projects)

## Why AlaSQL?
AlaSQL can apply SQL on JavaScript arrays and objects, including following operations:

* Can store,
* retrieve,
* sort,
* and iterate through JSON data,
* with a clean API,
* supports SQL
* and many other operations, like support of Local Storage and Indexed DB.

It has many functions for data manipulation in JSON format, including uploading and downloading JSON data.
```js
    // Load and process data
    alasql('SELECT * FROM JSON('mydata.json') GROUP BY name WHERE lastname LIKE "A%" \
                WHERE city = "London"', [], function(res1){
       console.log(res1);
    });

    // Process data on JSON arrays
    var data = [{a:1,b:10}, {a:2,b:20}, {a:1,b:30}];
    var res2 = alasql('SELECT a, SUM(b) AS b FROM ? GROUP BY a',[data]);
```
You can  try it [at jsFiddle](http://jsfiddle.net/agershun/30to2rh8/1/).

