# The AlaSQL Wiki

**To get an overview please have a look at the [[README]] section. **

**To get inspired try: [[Getting started]].**

**Check out [what other people say](People) about AlaSQL.**

### About AlaSQL


AlaSQL is a JavaScript SQL database library designed for:

* JavaScript [data manipulation](Data manipulation) and advanced filtering, grouping and joining
* Client-side [SQL database](Sql database) with persistence
* Fast data processing for BI and ERP applications
* Easy [ETL](Etl) (extract, transfer, and loading) data in [CSV](Csv), [XLSX](Xlsx), and other formats
* It works in all major browsers,  Node.js, and mobile applications

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




### AlaSQL Q&A
* [Data manipulation](Data manipulation) - array filtering, grouping, ordering
* [Data import and export](Import-export) - [TXT](Txt), [CSV](Csv), [TSV/TAB](Tsv)/, [XLS](Xls), 
[XLSX](Xlsx), [HTML](Html), [JSON](Json) 
* [Search in JSON arrays and objects](JSON)
* SQL for [JavaScript frameworks and libraries](JavaScript Frameworks):
 * Platforms: [Apache Cordova](Apache Cordova), [Ionic](Ionic), [Windows 8](Windows 8)
 * Frameworks: [Angular.js](Angular.js), 
 * Maps and diagrams: [d3.js](d3.js), [Google Maps](Google maps)
 * Charts: [Highcharts.js](Highcharts.js), [Google Charts](Google Charts) 
 * Spreadsheets: [Microsoft Excel](XLSX), [Google Docs Spreadsheets](Google Spreadsheets) 
 * Grid: [Handsontable.js](Handsontable.js)
 * Formatting: [Numeral.js](Numeral.js), [Moment.js](Moment.js), [Sprintf.js](Sprintf.hs)
* [SQL database](Sql database) - in-memory database + [AlaSQL FileStorage](FileStorage) persistence engine
* [SQL queries](SQL queries)
* [External databases](External databases) - [IndexedDB](IndexedDB), [Local Storage](LocalStorage), and [SQLite](SQLite) integration

### AlaSQL Documentation
* [About AlaSQL](About)
* [Installation](Installation)
* [Getting started](Getting started)
* [Supported SQL statements](Sql)
* [Functions](Functions)
* [JavaScript API](Api)
* [Webworker version](Webworker)
* [LINQ fluent interface](Fluent Interface)
* [Import and export functions](Import export)
* [Options](AlaSQL Options)
* [Errors processing](Errors)
* [Internal structure](Internal Structure)
* [Performance](Performance)
* [TypeScript](TypeScript)
* [SQL-99 compatibility](SQL-99), [SQL-99 keywords](SQL keywords), [AlaSQL keywords](AlaSQL Keywords)
* ["User Manual"](http://www.slideshare.net/AndreyGershun/alasql-manual-141220-1) - PowerPoint presentation
* SlideShare [AlaSQL.js - fast JavaScript in-memory SQL database](http://www.slideshare.net/AndreyGershun/alasqljsfast-javascript-inmemory-sql-database)
* SlideShare [SQL and NoSQL in AlaSQL database](http://www.slideshare.net/AndreyGershun/sql-and-nosql-in-alasql)
* [Quirky things](Quirky) about AlaSQL



### Command-Line Utilities
* [alacon](Alacon) - command-line utility for text and data files processing with SQL
* [alaserver](Alaserver) - simple SQL server based on AlaSQL

### Development 
* [How to setup environment for AlaSQL development?](How to setup environment for AlaSQL development)
* [How to assemble AlaSQL?](How to assemble AlaSQL)
* [How to prepare new release?](How to release)

### Sandbox
* [AlaSQL Console](http://alasql.org/console/alaconsole.html)

Unsure if AlaSQL fit your needs? Chekout the [other JavaScript SQL databases](Similar-Projects)
