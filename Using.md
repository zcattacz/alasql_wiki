# USING

Syntax:
```sql
    FROM table1 JOIN table USING column1, column2, ...
```

This ```USING``` clause is equivalent of the next ```ON``` clause:
```sql
    FROM table1 JOIN table ON table1.column1 = table2.column1 AND table1.column2 = table1.column2
```

In AlaSQL you can use ```USING``` clause like in this example:

```sql
    CREATE TABLE one (a INT, b INT);
    INSERT INTO one VALUES (1,10),(2,20);
    CREATE TABLE two (a INT, c INT);
    INSERT INTO two VALUES (1,100),(2,200);
    SELECT one.a, b, c FROM one JOIN two USING a;
```

See also: [JOIN](Join), [ON](On)