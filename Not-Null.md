# NOT NULL

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