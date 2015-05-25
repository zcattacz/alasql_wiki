# USING

In AlaSQL you can use ```USING``` clause like in this example:

```sql
    CREATE TABLE one (a INT, b INT);
    INSERT INTO one VALUES (1,10),(2,20);
    CREATE TABLE two (a INT, c INT);
    INSERT INTO two VALUES (1,100),(2,200);
    SELECT one.a, b, c FROM one JOIN two USING a;
```