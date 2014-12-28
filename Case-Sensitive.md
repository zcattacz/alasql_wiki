## Case Sensitive

Case sensitive words:
* Database names
* Table names
* Column names
* User-defined functions
* User-defined aggregator functions
* JSON properties and functions
* JavaScript classes

Different:
```sql
    SELECT * FROM city
    SELECT * FROM City
    SELECT * FROM CITY
```
## Case Insensitive

Case insensitive words:
* SQL Keywords (like SELECT) 
* Standard functions (like LEN)
* Standard aggregators (like SUM)
* External database engines (like INDEXEDDB)
* FROM-functions (like TXT)
* INTO-functions (like XLSX)

The following statements are the same:
```sql
    SELECT * FROM city
    select * from city
```




