# Keyword `COUNT`


Summing aggregator.

Syntax:
```sql
    COUNT([DISTINCT] expression | *)
```

AlaSQL supports ```COUNT()``` aggregator:
```sql
    SELECT COUNT(*) FROM one;
    SELECT COUNT(a) FROM one;
```

Also you can use ```COUNT()``` with ```DISTINCT``` keyword to count all non repeated values:
```sql
    SELECT COUNT(DISTINCT a) FROM one;
```