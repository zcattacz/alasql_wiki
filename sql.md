# SQL Statements Supported by Alasql

* [ALTER TABLE](sql/alter-table.md)
 * [ALTER TABLE ADD COLUMN](sql/add-column.md)
 * [ALTER TABLE MODIFY COLUMN](sql/modify-column.md)
 * [ALTER TABLE DROP COLUMN](sql/drop-column.md)
 * [ALTER TABLE RENAME TABLE](sql/rename-table.md)
* [BEGIN TRANSACTION](sql/begin-transaction.md)
* [BACKUP DATABASE](sql/backup-database.md)
* [COMMIT TRANSACTION](sql/commit-transaction.md)
* [CREATE]()
 * [CREATE DATABASE](sql/create-database.md)
 * [CREATE INDEX](sql/create-index.md)
 * [CREATE TABLE](sql/create-table.md)
  * Column Types
  	* JavaScript data types
  	  * String
  	  * Number
  	  * Boolean
  	  * Date and ISODate
  	* ANSI SQL types
  	* SQLite, Oracle, MySQL, SQL Server, Postgress data types mapping
  * Column constraints
    * PRIMARY KEY
    * FOREIGN KEY
    * DEFAULT
    * NULL / NOT NULL
    * AUTO_INCREMENT, IDENTITY
    * CHECK
  * Constraints
    * PRIMARY KEY
    * FOREIGN KEY
 * [CREATE TRIGGER](create-trigger.md)
 * [CREATE VIEW](sql/create-view.md)
* [DELETE](sql/delete.md)
* [DROP]()
 * [DROP DATABASE](sql/drop-database.md)
 * [DROP INDEX](sql/drop-index.md)
 * [DROP TABLE](sql/drop-table.md)
 * [DROP TRIGGER](sql/drop-trigger.md)
 * [DROP VIEW](sql/drop-view.md)
* [INSERT](sql/insert.md)
 * [INSERT SELECT](sql/insert-select.md)
 * [INSERT VALUES](sql/insert-values.md)
 * [INSERT DEFAULT VALUES](sql/insert-default-values.md) 
* [RENAME TABLE](sql/rename-table.md) (see also ALTER TABLE RENAME TABLE)
* [RESTORE DATABASE](sql/restore-database.md)
* [ROLLBACK TRANSACTION](sql/rollback.md)
* [SELECT](sql/select.md)
 * [TOP](sql/top.md)
 * [DISTINCT](sql/distinct.md)
 * [INTO](sql/into.md)
 * [FROM](sql/from.md)
 * [JOIN](sql/join.md)
 * [GROUP BY](sql/group-by.md)
 * [HAVING](sql/having.md)
 * [ORDER BY](sql/order-by.md)
 * [LIMIT](sql/limit.md)
 * [OFFSET](sql/offset.md)
 * [UNION]()
 * [UNION ALL]()
 * [INTERSECT]()
 * [EXCEPT]()
* [SHOW]()
 * [SHOW CREAET TABLE](sql/show-create-table.md)
 * [SHOW COLUMNS](sql/show-columns.md)
 * [SHOW DATABASES](sql/show-databases.md)
 * [SHOW INDEX](sql/show-index.md)
 * [SHOW TABLES](sql/show-tables.md)
* [UPDATE](sql/update.md)
* [USE DATABASE](sql/use-database.md)

* Operators
 * Number
  * + - * / %
 * String 
  * +
 * Comparing
  * = != < <= > >=
  * BETWEEN, NOT BETWEEN
 * Null
   * IS NULL, IS NOT NULL
* SQL-Functions
 * [ABS()](sql/abs.md)
* Complex Operators
  * EXISTS, NOT EXISTS
  * IN, NOT IN
  * SOME, ANY
  * ALL
* Aggregators
 * [SUM()](sql/sum.md) 
 * [COUNT()](sql/count.md) 
 * [AVG()](sql/avg.md) 
 * [MIN()](sql/min.md) 
 * [MAX()](sql/max.md) 
 * [FIRST()](sql/first.md) 
 * [LAST()](sql/last.md) 
* [Groupping functions](sql/group-by.md)
 * [CUBE()](sql/cube.md)
 * [ROLLUP()](sql/rollup.md)
 * [GROUPING SETS()](sql/grouping-sets.md)
* [Standard functions](sql/functions.md)
* [User-defined SQL functions](sql/user-defined-fn.md)
