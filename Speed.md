# Speed - We like it fast 

AlaSQL is very focused on speed and we make sure to use all the tricks we can find to make javascript spit out your results as quick as possible. For example:

* Queries are cached as compiled functions. 
* Joined tables are pre-indexed
* ```WHERE``` expressions are pre-filtered for joins

The results are good. Check out AlaSQL vs. other javaScript SQL databases: 

* **2x speed** [compared to SQL.js](http://jsperf.com/sql-js-vs-alasql-js/10) selecting with `SUM`, `JOIN`, and `GROUP BY`.

* **2x speed** [compared to WebSQL](http://jsperf.com/alasql-js-vs-websql/7) selecting with `SUM`, `JOIN`, and `GROUP BY` (in-memory opperations for WebSQL - see [this discussion](https://github.com/agershun/alasql/issues/47))

* **1.5x speed** [compared to Linq](http://jsperf.com/alasql-vs-linq-on-groupby) for `GROUP BY` on 1,048,576 rows

----

**More tests **

Every part must be optimized, so lets compare some cases where you would often use another library:

* Sorting with [AlaSQL vs Lodash vs Underscore vs. vanilla js](http://jsperf.com/alasql-vs-lodash-sort/6) - Sorting via SQL does not ned to be so far from vanilla javascript speed
* Finding the right data [AlaSQL vs. CrossFilter](http://jsperf.com/alasql-vs-crossfilter)
* Finding the right data [AlaSQL vs. CrossFilter 2](http://jsperf.com/alasql-vs-crossfilter-athletic-data)
* Grouping [AlaSQL vs. handcrafted javacsript](http://jsperf.com/javascript-array-grouping/10) - based on SatckOverflow [question on grouping](http://stackoverflow.com/questions/6781722/fast-grouping-of-a-javascript-array).


