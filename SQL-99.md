# SQL-99 core features in AlaSQL

The following table lists all features included in Core SQL-99 ([source](http://developer.mimer.com/validator/parser99/core-sql-99.tml)) and thier support in AlaSQL.

Feature ID | SQL-99 Feature Name | AlaSQL Support
----------- | ------------------- | -----------------
B011 | Embedded Ada *) | No
B012 | Embedded C *) | No
B013 | Embedded COBOL *) | No
B014 | Embedded Fortran *) | No
B015 | Embedded MUMPS *) | No
B016 | Embedded Pascal *) | No
B017 | Embedded PL/I 1 *) | No
E011 | Numeric data types | 
E011-01 | INTEGER and SMALLINT data types (including all spellings) | Yes*
E011-02 | REAL, DOUBLE PRECISON, and FLOAT data types | Yes*
E011-03 | DECIMAL and NUMERIC data types | No*
E011-04 | Arithmetic operators | Yes
E011-05 | Numeric comparison | Yes
E011-06 | Implicit casting among the numeric data types | Yes
E021 | Character data types | 
E021-01 | CHARACTER data type (including all its spellings) | Yes*
E021-02 | CHARACTER VARYING data type (including all its spellings) | Yes*
E021-03 | Character literals | Yes
E021-04 | CHARACTER_LENGTH function | Yes
E021-05 | OCTET_LENGTH function | No
E021-06 | SUBSTRING function | Yes*
E021-07 | Character concatenation | Yes
E021-08 | UPPER and LOWER functions | Yes
E021-09 | TRIM function | Yes
E021-10 | Implicit casting among the character data types | Yes
E021-11 | POSITION function | ?
E011-12 | Character comparison | Yes
E031 | Identifiers | 
E031-01 | Delimited identifiers | Yes
E031-02 | Lower case identifiers | Yes
E031-03 | Trailing underscore | Yes
E051 | Basic query specification | 
E051-01 | SELECT DISTINCT | Yes
E051-02 | GROUP BY clause | Yes
E051-04 | GROUP BY can contain columns not in select-list | Yes
E051-05 | Select list items can be renamed | Yes
E051-06 | HAVING clause | Yes
E051-07 | Qualified * in select list | Yes
E051-08 | Correlation names in the FROM clause | Yes
E051-09 | Rename columns in the FROM clause | Yes
E061 | Basic predicates and search conditions | 
E061-01 | Comparison predicate | Yes
E061-02 | BETWEEN predicate | Yes
E061-03 | IN predicate with list of values | Yes
E061-04 | LIKE predicate | Yes
E061-05 | LIKE predicate: ESCAPE clause | Yes*
E061-06 | NULL predicate | Yes
E061-07 | Quantified comparison predicate | Yes
E061-08 | EXISTS predicate | Yes
E061-09 | Subqueries in comparison predicate | Yes
E061-11 | Subqueries in IN predicate | Yes
E061-12 | Subqueries in quantified comparison predicate | Yes
E061-13 | Correlated subqueries | Yes
E061-14 | Search condition | Yes
E071 | Basic query expressions | 
E071-01 | UNION DISTINCT table operator | Yes
E071-02 | UNION ALL table operator | Yes
E071-03 | EXCEPT DISTINCT table operator | Yes
E071-05 | Columns combined via table operators need not have exactly the same data type | Yes
E071-06 | Table operators in subqueries | Yes
E081 | Basic Privileges | 
E081-01 | SELECT privilege at the table level | No
E081-02 | DELETE privilege | No
E081-03 | INSERT privilege at the table level | No
E081-04 | UPDATE privilege at the table level | No
E081-05 | UPDATE privilege at the column level | No
E081-06 | REFERENCES privilege at the table level | No
E081-07 | REFERENCES privilege at the column level | No
E081-08 | WITH GRANT OPTION | No
E081-09 | USAGE privilege | No
E081-10 | EXECUTE privilege | No
E091 | Set functions | 
E091-01 | AVG | Yes
E091-02 | COUNT | Yes
E091-03 | MAX | Yes
E091-04 | MIN | Yes
E091-05 | SUM | Yes
E091-06 | ALL quantifier | Yes
E091-07 | DISTINCT quantifier | Yes
E101 | Basic data manipulation | 
E101-01 | INSERT statement | Yes
E101-03 | Searched UPDATE statement | Yes
E101-04 | Searched DELETE statement | Yes
E111 | Single row SELECT statement | Yes
E121 | Basic cursor support | 
E121-01 | DECLARE CURSOR | No
E121-02 | ORDER BY columns need not be in select list | No
E121-03 | Value expressions in ORDER BY clause | No
E121-04 | OPEN statement | No
E121-06 | Positioned UPDATE statement | No
E121-07 | Positioned DELETE statement | No
E121-08 | CLOSE statement | No
E121-10 | FETCH statement: implicit NEXT | No
E121-17 | WITH HOLD cursors | No
E131 | Null value support (nulls in lieu of values) | Yes
E141 | Basic integrity constraints | 
E141-01 | NOT NULL constraints | Yes
E141-02 | UNIQUE constraints of NOT NULL columns | Yes
E141-03 | PRIMARY KEY constraints | Yes
E141-04 | Basic FOREIGN KEY constraint with the NO ACTION default | Yes*
E141-06 | CHECK constraints | Yes
E141-07 | Column defaults | Yes
E141-08 | NOT NULL inferred on PRIMARY KEY | ?
E141-10 | Names in a foreign key can be specified in any order | ?
E151 | Transaction support | 
E151-01 | COMMIT statement | No
E151-02 | ROLLBACK statement | No
E152 | Basic SET TRANSACTION statement | 
E152-01 | SET TRANSACTION statement: ISOLATION LEVEL SERIALIZABLE clause | No
E152-02 | SET TRANSACTION statement: READ ONLY and READ WRITE clauses | No
E153 | Updatable queries with subqueries | No
E161 | SQL comments using leading double minus | Yes
E171 | SQLSTATE support | No
F021 | Basic information schema | 
F021-01 | COLUMNS view | Yes
F021-02 | TABLES view | Yes
F021-03 | VIEWS view | Yes
F021-04 | TABLE_CONSTRAINTS view | No
F021-05 | REFERENTIAL_CONSTRAINTS view | No
F021-06 | CHECK_CONSTRAINTS view | No
F031 | Basic schema manipulation | 
F031-01 | CREATE TABLE statement to create persistent base tables | Yes
F031-02 | CREATE VIEW statement | Yes
F031-03 | GRANT statement | No
F031-04 | ALTER TABLE statement: ADD COLUMN clause | Partial
F031-13 | DROP TABLE statement: RESTRICT clause | Partial
F031-16 | DROP VIEW statement: RESTRICT clause | Partial
F031-19 | REVOKE statement: RESTRICT clause | No
F041 | Basic joined table | 
F041-01 | Inner join (but not necessarily the INNER keyword) | Yes
F041-02 | INNER keyword | Yes
F041-03 | LEFT OUTER JOIN | Yes
F041-04 | RIGHT OUTER JOIN | Yes
F041-05 | Outer joins can be nested | ?
F041-07 | The inner table in a left or right outer join can also be used in an inner join | ?
F041-08 | All comparison operators are supported (rather than just =) | Yes
F051 | Basic date and time | 
F051-01 | DATE data type (including DATE literal) | Yes
F051-02 | TIME data type (including TIME literal) with fractional seconds precision of 0 | Yes
F051-03 | TIMESTAMP data type (including TIMESTAMP literal) with fractional seconds precision of 0 and 6 | Yes
F051-04 | Comparison predicate on DATE, TIME, and TIMESTAMP data types | Yes
F051-05 | Explicit CAST between datetime types and character types | Yes
F051-06 | CURRENT_DATE | No
F051-07 | LOCALTIME | No
F051-08 | LOCALTIMESTAMP | No
F081 | UNION and EXCEPT in views | ?
F131 | Grouped operations | 
F131-01 | WHERE, GROUP BY, and HAVING clauses supported in queries with grouped views | Yes
F131-02 | Multiple tables supported in queries with grouped views | Yes
F131-03 | Set functions supported in queries with grouped views | Yes
F131-04 | Subqueries with GROUP BY and HAVING clauses and grouped views | Yes
F131-05 | Single row SELECT with GROUP BY and HAVING clauses and grouped views | Yes
F181 | Multiple module support | No
F201 | CAST function | Yes
F221 | Explicit defaults | Yes
F261 | CASE expression | 
F261-01 | Simple CASE | Yes
F261-02 | Searched CASE | Yes
F261-03 | NULLIF | Yes
F261-04 | COALESCE | Yes
F311 | Schema definition statement | 
F311-01 | CREATE SCHEMA | Partial
F311-02 | CREATE TABLE for persistent base tables | Yes
F311-03 | CREATE VIEW | Yes
F311-04 | CREATE VIEW: WITH CHECK OPTION | No (only syntax)
F311-05 | GRANT statement | No
F471 | Scalar subquery values | Yes
F481 | Expanded NULL predicate | Yes
F501 | Features and conformance views | 
F501-01 | SQL_FEATURES view | No
F501-02 | SQL_SIZING view | No
F501-03 | SQL_LANGUAGES view | No
F812 | Basic flagging | No
S011 | Distinct data types | 
S011-01 | USER_DEFINED_TYPES view | No
T321 | Basic SQL-invoked routines | 
T321-01 | User-defined functions with no overloading | Yes
T321-02 | User-defined stored procedures with no overloading | No
T321-03 | Function invocation | No
T321-04 | CALL statement | No
T321-05 | RETURN statement | No
T321-06 | ROUTINES view | No
T321-07 | PARAMETERS view | No

