# NOT NULL

### IS NOT NULL operator
You can use ```IS NOT NULL``` operator to check if value is [NULL](Null)([undefined](Undefined)).
```sql
IF OBJECT_ID('dbo.Parts') IS NOT NULL
  DROP TABLE dbo.Parts;
GO
```

### NOT NULL column constraint
AlaSQL supports ```NOT NULL``` column constraints.

Please see this example:
```
CREATE TABLE dbo.Cities (
  cityid  CHAR(3)     NOT NULL PRIMARY KEY,
  city    VARCHAR(30) NOT NULL,
  region  VARCHAR(30) NULL,
  country VARCHAR(30) NOT NULL
);
```