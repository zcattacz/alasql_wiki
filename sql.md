# Alasql SQL Statements

* [Single and multiple SQL statements](Multiple Statements)

## Short list by category

Data query

* [SELECT](Select)

Data manipulation

* [INSERT](Insert)
* [UPDATE](Update)
* [DELETE](Delete)

Data definition

* [CREATE TABLE](Create Table)
* [ALTER TABLE](Alter Table)
* [DROP TABLE](Drop Table)

Database

* [USE DATABASE](Use Database)
* [CREATE DATABASE(Create Database)
* [DROP DATABASE](Drop Database)

External database
* [ATTACH DATABASE](Attach Database)
* [DETACH DATABASE](Detach Database)

Transactions
* [BEGIN](Begin Transaction)
* [COMMIT](Commit Transaction)
* [ROLLBACK](Rollback)

Show

* [SHOW DATABASES](Show Databases)
* [SHOW TABLES](Show Tables)
* [SHOW CREATE TABLE](Show Create Table)

Program
* [SET](Set)
* [SOURCE](Source)

Debug
* [ASSERT](Assert)

Information
* [HELP](Help)

## Full list

* [ASSERT](Assert)
* [ATTACH](Attach)
* ALTER TABLE
 * [ALTER TABLE ADD COLUMN](Add Column)
 * [ALTER TABLE MODIFY COLUMN](Modify Column)
 * [ALTER TABLE DROP COLUMN](Drop Column)
 * [ALTER TABLE RENAME TABLE](Rename Table)
* [BEGIN TRANSACTION](Begin Transaction)
* [COMMIT TRANSACTION](Commit Transaction)
* CREATE
 * [CREATE DATABASE](Create Database)
 * [CREATE TABLE](Create Table)
  * Column Types
  	* JavaScript data types
  	  * String
  	  * Number
  	  * Boolean
  	  * Date and ISODate
          * Emun
  	* ANSI SQL types
  	* SQLite, Oracle, MySQL, SQL Server, Postgres data types mapping
  * Column constraints
    * PRIMARY KEY
    * FOREIGN KEY
    * DEFAULT
    * NULL / NOT NULL
    * AUTO_INCREMENT, IDENTITY
    * CHECK
* [DELETE](Delete)
* DROP
 * [DROP DATABASE](Drop Database)
 * [DROP TABLE](Drop Table)
* INSERT
 * [INSERT SELECT](Insert Select)
 * [INSERT VALUES](Insert Values)
 * [INSERT DEFAULT VALUES](Insert Default Values) 
* [RENAME TABLE](Rename Table)
* [ROLLBACK TRANSACTION](Rollback Transaction)
* [SELECT](Select)
 * [TOP](Top)
 * [DISTINCT](Distinct)
 * [INTO](Into)
 * [FROM](From)
 * [JOIN](Join)
 * [GROUP BY](Group By)
 * [HAVING](Having)
 * [ORDER BY](Order By)
 * [LIMIT](Limit)
 * [OFFSET](Offset)
 * [UNION](Union)
 * [UNION ALL](Union All)
 * [INTERSECT](Intersect)
 * [Minus](Except),[EXCEPT](Except)
* SHOW
 * [SHOW CREATE TABLE](Show Create Table)
 * [SHOW COLUMNS](Show Columns)
 * [SHOW DATABASES](Show Databases)
 * [SHOW TABLES](Show Tables)
* [UPDATE](Update)
* [USE DATABASE](Use Database)

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
 * [SUM()](Sum) 
 * [COUNT()](Count) 
 * [MIN()](Min) 
 * [MAX()](Max) 
 * [FIRST()](First 
 * [LAST()](Last) 
 * [AGGR()](Aggr)
 * [ARRAY()](Array)
* Groupping functions
 * [CUBE()](Cube)
 * [ROLLUP()](Rollup)
 * [GROUPING SETS()](Grouping Sets)
* [Standard functions](Functions)
* [User-defined SQL functions](User Defined Functions)
