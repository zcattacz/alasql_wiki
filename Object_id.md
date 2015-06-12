# OBJECT_ID

AlaSQL emulates [TSQL](Tsql) `OBJECT_ID()` function:
```sql
IF OBJECT_ID('dbo.Parts') IS NOT NULL
  DROP TABLE dbo.Parts;
GO 
```
This functions can be used to check if table or view object is in the current database.