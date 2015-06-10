## Speed - We like it fast 
Thats why we make sure to use all the tricks we can find to make javascript spit out your results as quick as possible. Among other things we make sure that: 

* Queries are cached as compiled functions. 
* Joined tables are pre-indexed
* ```WHERE``` expressions are pre-filtered for joins

But dont take our word for it. Check out AlaSQL vs other JavaScript SQL databases: 

* [AlaSQL vs. WebSQL](http://jsperf.com/alasql-js-vs-websql/7) - Mixing `SELECT`, `SUM`, `JOIN`, and `GROUP BY` on fake data (in-memory opperations for both - see [this discussion](https://github.com/agershun/alasql/issues/47))
* [AlaSQL vs. SQL.js](http://jsperf.com/sql-js-vs-alasql-js/9) - Mixing `SELECT`, `SUM`, `JOIN`, and `GROUP BY` on fake data
* [AlaSQL vs. Linq](http://jsperf.com/alasql-vs-linq-on-groupby) - `GROUP BY` on 1,048,576 rows

Every part must be optimized, so lets compare some cases where you would often use another library:

* Sorting with [Alasql vs Lodash vs Underscore vs. vanilla js](http://jsperf.com/alasql-vs-lodash-sort/6) - Sorting via SQL does not ned to be so far from vanilla javascript speed
* Finding the right data [AlaSQL vs. CrossFilter](http://jsperf.com/alasql-vs-crossfilter)
* Finding the right data [AlaSQL vs. CrossFilter 2](http://jsperf.com/alasql-vs-crossfilter-athletic-data)
* Grouping [AlaSQL vs. handcrafted javacsript](http://jsperf.com/javascript-array-grouping/10) - based on SatckOverflow [question on grouping](http://stackoverflow.com/questions/6781722/fast-grouping-of-a-javascript-array).


