# SQLlogic test results for AlaSQL 0.0.46

_2015-06-26T13:24:23.530Z_

Results from 125 test files

-----------------------------
### ` test/evidence/in1.test `

#### ✔ Ran 0 tests

* 0 failed
* 0% was OK

Time: 18ms

-----------------------------
### ` test/evidence/in2.test `

#### ✔ Ran 50 tests

* 0 failed
* 100% was OK

Time: 58ms

-----------------------------
### ` test/evidence/slt_lang_aggfunc.test `

#### ✔ Ran 5 tests

* 0 failed
* 100% was OK

Time: 7ms

-----------------------------
### ` test/evidence/slt_lang_createtrigger.test `

#### ✔ Ran 5 tests

* 0 failed
* 100% was OK

Time: 6ms

-----------------------------
### ` test/evidence/slt_lang_createview.test `

```
CREATE TEMP VIEW view2 AS SELECT x FROM t1 WHERE x>0

Parse error on line 1:
CREATE TEMP VIEW view2 AS SELECT
------------^
Expecting 'LITERAL', 'BRALITERAL', 'EOF', 'SEMICOLON', 'GO', 'EndTransaction', 'WITH', 'COMMA', 'AS', 'LPAR', 'RPAR', 'UNIQUE', 'SELECT', 'INDEX', 'INTO', 'STRING', 'FROM', 'CROSS', 'OUTER', 'DOT', 'NATURAL', 'JOIN', 'INNER', 'LEFT', 'RIGHT', 'FULL', 'SEMI', 'ANTI', 'ON', 'USING', 'WHERE', 'GROUP', 'HAVING', 'UNION', 'EXCEPT', 'INTERSECT', 'ORDER', 'DIRECTION', 'COLLATE', 'LIMIT', 'TD', 'TH', 'NUMBER', 'STAR', 'JAVASCRIPT', 'NSTRING', 'NULL', 'COLON', 'END', 'WHEN', 'THEN', 'ELSE', 'LIKE', 'NOT_LIKE', 'PLUS', 'MINUS', 'SLASH', 'MODULO', 'CARET', 'ARROW', 'GT', 'GE', 'LT', 'LE', 'EQ', 'EQEQ', 'EQEQEQ', 'NE', 'NEEQEQ', 'NEEQEQEQ', 'AND', 'OR', 'NOT', 'IN', 'BETWEEN', 'NOT_BETWEEN', 'IS', 'DOUBLECOLON', 'UPDATE', 'SET', 'DELETE', 'INSERT', 'VALUES', 'DEFAULT', 'CREATE', 'ENGINE', 'AUTO_INCREMENT', 'CHARSET', 'IF', 'CHECK', 'PRIMARY', 'KEY', 'FOREIGN', 'REFERENCES', 'ColumnConstraints', 'ENUM', 'IDENTITY', 'DROP', 'ALTER', 'RENAME', 'TO', 'ADD', 'MODIFY', 'ATTACH', 'DATABASE', 'DETACH', 'USE', 'SHOW', 'DATABASES', 'HELP', 'SOURCE', 'ASSERT', 'RCUR', 'RBRA', 'OFF', 'COMMIT', 'ROLLBACK', 'BEGIN', 'WHILE', 'CONTINUE', 'BREAK', 'PRINT', 'REQUIRE', 'DECLARE', 'TRUNCATE', 'MERGE', 'OUTPUT', got 'VIEW'
```

#### ☓ Ran 15 tests

* 2 failed
* 86% was OK

Time: 12ms

-----------------------------
### ` test/evidence/slt_lang_dropindex.test `

#### ✔ Ran 6 tests

* 0 failed
* 100% was OK

Time: 3ms

-----------------------------
### ` test/evidence/slt_lang_droptable.test `

#### ✔ Ran 9 tests

* 0 failed
* 100% was OK

Time: 6ms

-----------------------------
### ` test/evidence/slt_lang_droptrigger.test `

#### ✔ Ran 5 tests

* 0 failed
* 100% was OK

Time: 4ms

-----------------------------
### ` test/evidence/slt_lang_dropview.test `

#### ✔ Ran 11 tests

* 0 failed
* 100% was OK

Time: 6ms

-----------------------------
### ` test/evidence/slt_lang_reindex.test `

#### ✔ Ran 5 tests

* 0 failed
* 100% was OK

Time: 4ms

-----------------------------
### ` test/evidence/slt_lang_replace.test `

#### ✔ Ran 0 tests

* 0 failed
* 0% was OK

Time: 1ms

-----------------------------
### ` test/evidence/slt_lang_update.test `

#### ✔ Ran 25 tests

* 0 failed
* 100% was OK

Time: 22ms

-----------------------------
### ` test/index/between/1/slt_good_0.test `

