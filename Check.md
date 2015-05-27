# CHECK

AlaSQL supports ```CHECK``` table constraints.

Syntax:
```sql
    CREATE TABLE table (
        column type CHECK expression
    );
```

For example:
```sql
    CREATE TABLE dbo.Employees (
      empid   INT         NOT NULL PRIMARY KEY,
      mgrid   INT         NULL REFERENCES dbo.Employees,
      empname VARCHAR(25) NOT NULL,
      salary  MONEY       NOT NULL,
      CHECK (empid <> mgrid)
    );
```

You can use this constraint for whole table or for separate fields.

See also: [CONSTRAINT](Constraint)