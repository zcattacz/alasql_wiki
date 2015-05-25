# NULL

AlaSQL supports ```NULL``` keyword.

### NULL Constraint

You can set ```NULL``` column constraint. In this example the ```partname``` column can accept ```NULL``` values.
```sql
CREATE TABLE dbo.Parts (
  partid   INT         NOT NULL PRIMARY KEY,
  partname VARCHAR(25) NULL
);
```