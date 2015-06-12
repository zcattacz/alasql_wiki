# Keyword `UNIQUE`

AlaSQL supports ```UNIQUE``` constraints.

For example:
```sql
CREATE TABLE dbo.BOM
(
  partid     INT           NOT NULL REFERENCES dbo.Parts,
  assemblyid INT           NULL     REFERENCES dbo.Parts,
  unit       VARCHAR(3)    NOT NULL,
  qty        DECIMAL(8, 2) NOT NULL,
  UNIQUE(partid, assemblyid),
  CHECK (partid <> assemblyid)
);
```

