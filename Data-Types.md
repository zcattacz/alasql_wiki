# Data Types

### Basic data types

Integer ([number](Number) with truncation)
* smallint
* integer
* bigint

Decimal ([number](Number))
* decimal
* numeric

Floating-Point ([number](Number))
* real
* double precision

Serial (number with [AUTO_INCREMENT](Auto_increment))
* smallserial
* serial
* bigserial (maximum 9999999999999998, [not 9223372036854775807 like in Postgres](http://www.postgresql.org/docs/9.4/static/datatype-numeric.html))

Monetary ([number](Number))
* money

Character (string)
* character varying(n), varchar(n), nvarchar(n)
* character(n), char(n), nchar(n)
* text

Binary Data Types
* TBD

Date/Time ([string](String) and [Date](Date))
* date - string
* time - string
* interval ([number](Number)) - in milliseconds
* [Date](Date) - JavaScript Date object class

Boolean ([boolean](Boolean))
* boolean

### Complex data types

Enumeration (array of strings or numbers)
* enum

Geometric Types
* Not realized

Network Address Types
* Not realized

Bit String
* Not realized

Text Search
* tsvector - not realized
* tsquery - not realized

UUID ([string](String))
* UUID

XML ([object](Object) with special structure)
* xml - partially realized for [SEARCH](Search)
* html - not realized

JSON ([object](Object))
* json
* jsonb - not yet realized

Array ([object](Object))
* multidimensional array[] - not yet realized, but can be imitated with [JSON](Json) type

Composite ([object](Object))
* composite - not yet realized, but can be imitated with [JSON](Json) type. See also [CLASS](Class) type

Range ([object](Object))
* numrange - not yet realized
* tsrange - not yet realized
* daterange - not yet realized

OID 
* not realized yet

### Graph data types

Class (realized with tables)
* class

Object ([object](Object))
* object, json - JavaScript object class

Document ([object](Object))
* TBD

Object reference ([number](Number) or [string](String))
* TBD

Domain
* TBD


Pseudo 
* not yet realized












AlaSQL supports a number of standard SQL and JavaScript data types.