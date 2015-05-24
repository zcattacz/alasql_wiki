# SQL-99 core features in AlaSQL

The following table lists all features included in Core SQL-99 ([source](http://developer.mimer.com/validator/parser99/core-sql-99.tml)) and thier support in AlaSQL.
<table>
<tr><td>Feature ID<td>SQL-99 Feature Name<td>AlaSQL support
<tr><td>B011<td>Embedded Ada *)<td>No
<tr><td>B012<td>Embedded C *)<td>No
<tr><td>B013<td>Embedded COBOL *)<td>No
<tr><td>B014<td>Embedded Fortran *)<td>No
<tr><td>B015<td>Embedded MUMPS *)<td>No
<tr><td>B016<td>Embedded Pascal *)<td>No
<tr><td>B017<td>Embedded PL/I 1 *)<td>No
<tr><td>E011<td>Numeric data types<td>
<tr><td>E011-01<td>INTEGER and SMALLINT data types (including all spellings)<td>Yes*
<tr><td>E011-02<td>REAL, DOUBLE PRECISON, and FLOAT data types<td>Yes*
<tr><td>E011-03<td>DECIMAL and NUMERIC data types<td>No*
<tr><td>E011-04<td>Arithmetic operators<td>Yes
<tr><td>E011-05<td>Numeric comparison<td>Yes
<tr><td>E011-06<td>Implicit casting among the numeric data types<td>Yes
<tr><td>E021<td>Character data types<td>
<tr><td>E021-01<td>CHARACTER data type (including all its spellings)<td>Yes*
<tr><td>E021-02<td>CHARACTER VARYING data type (including all its spellings)<td>Yes*
<tr><td>E021-03<td>Character literals<td>Yes
<tr><td>E021-04<td>CHARACTER_LENGTH function<td>Yes
<tr><td>E021-05<td>OCTET_LENGTH function<td>No
<tr><td>E021-06<td>SUBSTRING function<td>Yes*
<tr><td>E021-07<td>Character concatenation<td>Yes
<tr><td>E021-08<td>UPPER and LOWER functions<td>Yes
<tr><td>E021-09<td>TRIM function<td>Yes
<tr><td>E021-10<td>Implicit casting among the character data types<td>Yes
<tr><td>E021-11<td>POSITION function<td>?
<tr><td>E011-12<td>Character comparison<td>Yes
<tr><td>E031<td>Identifiers<td>
<tr><td>E031-01<td>Delimited identifiers<td>Yes
<tr><td>E031-02<td>Lower case identifiers<td>Yes
<tr><td>E031-03<td>Trailing underscore<td>Yes
<tr><td>E051<td>Basic query specification<td>
<tr><td>E051-01<td>SELECT DISTINCT<td>Yes
<tr><td>E051-02<td>GROUP BY clause<td>Yes
<tr><td>E051-04<td>GROUP BY can contain columns not in select-list<td>Yes
<tr><td>E051-05<td>Select list items can be renamed<td>Yes
<tr><td>E051-06<td>HAVING clause<td>Yes
<tr><td>E051-07<td>Qualified * in select list<td>Yes
<tr><td>E051-08<td>Correlation names in the FROM clause<td>Yes
<tr><td>E051-09<td>Rename columns in the FROM clause<td>Yes
<tr><td>E061<td>Basic predicates and search conditions<td>
<tr><td>E061-01<td>Comparison predicate<td>Yes
<tr><td>E061-02<td>BETWEEN predicate<td>Yes
<tr><td>E061-03<td>IN predicate with list of values<td>Yes
<tr><td>E061-04<td>LIKE predicate<td>Yes
<tr><td>E061-05<td>LIKE predicate: ESCAPE clause<td>Yes*
<tr><td>E061-06<td>NULL predicate<td>Yes
<tr><td>E061-07<td>Quantified comparison predicate<td>Yes
<tr><td>E061-08<td>EXISTS predicate<td>Yes
<tr><td>E061-09<td>Subqueries in comparison predicate<td>Yes
<tr><td>E061-11<td>Subqueries in IN predicate<td>Yes
<tr><td>E061-12<td>Subqueries in quantified comparison predicate<td>Yes
<tr><td>E061-13<td>Correlated subqueries<td>Yes
<tr><td>E061-14<td>Search condition<td>Yes
<tr><td>E071<td>Basic query expressions<td>
<tr><td>E071-01<td>UNION DISTINCT table operator<td>Yes
<tr><td>E071-02<td>UNION ALL table operator<td>Yes
<tr><td>E071-03<td>EXCEPT DISTINCT table operator<td>Yes
<tr><td>E071-05<td>Columns combined via table operators need not have exactly the same data type<td>Yes
<tr><td>E071-06<td>Table operators in subqueries<td>Yes
<tr><td>E081<td>Basic Privileges<td>
<tr><td>E081-01<td>SELECT privilege at the table level<td>No
<tr><td>E081-02<td>DELETE privilege<td>No
<tr><td>E081-03<td>INSERT privilege at the table level<td>No
<tr><td>E081-04<td>UPDATE privilege at the table level<td>No
<tr><td>E081-05<td>UPDATE privilege at the column level<td>No
<tr><td>E081-06<td>REFERENCES privilege at the table level<td>No
<tr><td>E081-07<td>REFERENCES privilege at the column level<td>No
<tr><td>E081-08<td>WITH GRANT OPTION<td>No
<tr><td>E081-09<td>USAGE privilege<td>No
<tr><td>E081-10<td>EXECUTE privilege<td>No
<tr><td>E091<td>Set functions<td>
<tr><td>E091-01<td>AVG<td>Yes
<tr><td>E091-02<td>COUNT<td>Yes
<tr><td>E091-03<td>MAX<td>Yes
<tr><td>E091-04<td>MIN<td>Yes
<tr><td>E091-05<td>SUM<td>Yes
<tr><td>E091-06<td>ALL quantifier<td>Yes
<tr><td>E091-07<td>DISTINCT quantifier<td>Yes
<tr><td>E101<td>Basic data manipulation<td>
<tr><td>E101-01<td>INSERT statement<td>Yes
<tr><td>E101-03<td>Searched UPDATE statement<td>Yes
<tr><td>E101-04<td>Searched DELETE statement<td>Yes
<tr><td>E111<td>Single row SELECT statement<td>Yes
<tr><td>E121<td>Basic cursor support<td>
<tr><td>E121-01<td>DECLARE CURSOR<td>No
<tr><td>E121-02<td>ORDER BY columns need not be in select list<td>No
<tr><td>E121-03<td>Value expressions in ORDER BY clause<td>No
<tr><td>E121-04<td>OPEN statement<td>No
<tr><td>E121-06<td>Positioned UPDATE statement<td>No
<tr><td>E121-07<td>Positioned DELETE statement<td>No
<tr><td>E121-08<td>CLOSE statement<td>No
<tr><td>E121-10<td>FETCH statement: implicit NEXT<td>No
<tr><td>E121-17<td>WITH HOLD cursors<td>No
<tr><td>E131<td>Null value support (nulls in lieu of values)<td>Yes
<tr><td>E141<td>Basic integrity constraints<td>
<tr><td>E141-01<td>NOT NULL constraints<td>Yes
<tr><td>E141-02<td>UNIQUE constraints of NOT NULL columns<td>Yes
<tr><td>E141-03<td>PRIMARY KEY constraints<td>Yes
<tr><td>E141-04<td>Basic FOREIGN KEY constraint with the NO ACTION default<td>Yes*
<tr><td>E141-06<td>CHECK constraints<td>Yes
<tr><td>E141-07<td>Column defaults<td>Yes
<tr><td>E141-08<td>NOT NULL inferred on PRIMARY KEY<td>?
<tr><td>E141-10<td>Names in a foreign key can be specified in any order<td>?
<tr><td>E151<td>Transaction support<td>
<tr><td>E151-01<td>COMMIT statement<td>No
<tr><td>E151-02<td>ROLLBACK statement<td>No
<tr><td>E152<td>Basic SET TRANSACTION statement<td>
<tr><td>E152-01<td>SET TRANSACTION statement: ISOLATION LEVEL SERIALIZABLE clause<td>No
<tr><td>E152-02<td>SET TRANSACTION statement: READ ONLY and READ WRITE clauses<td>No
<tr><td>E153<td>Updatable queries with subqueries<td>No
<tr><td>E161<td>SQL comments using leading double minus<td>Yes
<tr><td>E171<td>SQLSTATE support<td>No
<tr><td>F021<td>Basic information schema<td>
<tr><td>F021-01<td>COLUMNS view<td>Yes
<tr><td>F021-02<td>TABLES view<td>Yes
<tr><td>F021-03<td>VIEWS view<td>Yes
<tr><td>F021-04<td>TABLE_CONSTRAINTS view<td>No
<tr><td>F021-05<td>REFERENTIAL_CONSTRAINTS view<td>No
<tr><td>F021-06<td>CHECK_CONSTRAINTS view<td>No
<tr><td>F031<td>Basic schema manipulation<td>
<tr><td>F031-01<td>CREATE TABLE statement to create persistent base tables<td>Yes
<tr><td>F031-02<td>CREATE VIEW statement<td>Yes
<tr><td>F031-03<td>GRANT statement<td>No
<tr><td>F031-04<td>ALTER TABLE statement: ADD COLUMN clause<td>Partial
<tr><td>F031-13<td>DROP TABLE statement: RESTRICT clause<td>Partial
<tr><td>F031-16<td>DROP VIEW statement: RESTRICT clause<td>Partial
<tr><td>F031-19<td>REVOKE statement: RESTRICT clause<td>No
<tr><td>F041<td>Basic joined table<td>
<tr><td>F041-01<td>Inner join (but not necessarily the INNER keyword)<td>Yes
<tr><td>F041-02<td>INNER keyword<td>Yes
<tr><td>F041-03<td>LEFT OUTER JOIN<td>Yes
<tr><td>F041-04<td>RIGHT OUTER JOIN<td>Yes
<tr><td>F041-05<td>Outer joins can be nested<td>?
<tr><td>F041-07<td>The inner table in a left or right outer join can also be used in an inner join<td>?
<tr><td>F041-08<td>All comparison operators are supported (rather than just =)<td>Yes
<tr><td>F051<td>Basic date and time<td>
<tr><td>F051-01<td>DATE data type (including DATE literal)<td>Yes
<tr><td>F051-02<td>TIME data type (including TIME literal) with fractional seconds precision of 0<td>Yes
<tr><td>F051-03<td>TIMESTAMP data type (including TIMESTAMP literal) with fractional seconds precision of 0 and 6<td>Yes
<tr><td>F051-04<td>Comparison predicate on DATE, TIME, and TIMESTAMP data types<td>Yes
<tr><td>F051-05<td>Explicit CAST between datetime types and character types<td>Yes
<tr><td>F051-06<td>CURRENT_DATE<td>No
<tr><td>F051-07<td>LOCALTIME<td>No
<tr><td>F051-08<td>LOCALTIMESTAMP<td>No
<tr><td>F081<td>UNION and EXCEPT in views<td>?
<tr><td>F131<td>Grouped operations<td>
<tr><td>F131-01<td>WHERE, GROUP BY, and HAVING clauses supported in queries with grouped views<td>Yes
<tr><td>F131-02<td>Multiple tables supported in queries with grouped views<td>Yes
<tr><td>F131-03<td>Set functions supported in queries with grouped views<td>Yes
<tr><td>F131-04<td>Subqueries with GROUP BY and HAVING clauses and grouped views<td>Yes
<tr><td>F131-05<td>Single row SELECT with GROUP BY and HAVING clauses and grouped views<td>Yes
<tr><td>F181<td>Multiple module support<td>No
<tr><td>F201<td>CAST function<td>Yes
<tr><td>F221<td>Explicit defaults<td>Yes
<tr><td>F261<td>CASE expression<td>
<tr><td>F261-01<td>Simple CASE<td>Yes
<tr><td>F261-02<td>Searched CASE<td>Yes
<tr><td>F261-03<td>NULLIF<td>Yes
<tr><td>F261-04<td>COALESCE<td>Yes
<tr><td>F311<td>Schema definition statement<td>
<tr><td>F311-01<td>CREATE SCHEMA<td>Partial
<tr><td>F311-02<td>CREATE TABLE for persistent base tables<td>Yes
<tr><td>F311-03<td>CREATE VIEW<td>Yes
<tr><td>F311-04<td>CREATE VIEW: WITH CHECK OPTION<td>No (only syntax)
<tr><td>F311-05<td>GRANT statement<td>No
<tr><td>F471<td>Scalar subquery values<td>Yes
<tr><td>F481<td>Expanded NULL predicate<td>Yes
<tr><td>F501<td>Features and conformance views<td>
<tr><td>F501-01<td>SQL_FEATURES view<td>No
<tr><td>F501-02<td>SQL_SIZING view<td>No
<tr><td>F501-03<td>SQL_LANGUAGES view<td>No
<tr><td>F812<td>Basic flagging<td>No
<tr><td>S011<td>Distinct data types<td>
<tr><td>S011-01<td>USER_DEFINED_TYPES view<td>No
<tr><td>T321<td>Basic SQL-invoked routines<td>
<tr><td>T321-01<td>User-defined functions with no overloading<td>Yes
<tr><td>T321-02<td>User-defined stored procedures with no overloading<td>No
<tr><td>T321-03<td>Function invocation<td>No
<tr><td>T321-04<td>CALL statement<td>No
<tr><td>T321-05<td>RETURN statement<td>No
<tr><td>T321-06<td>ROUTINES view<td>No
<tr><td>T321-07<td>PARAMETERS view<td>No
</table>
