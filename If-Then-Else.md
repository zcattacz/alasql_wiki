# IF THEN ELSE

```sql
    IF EXISTS(SELECT * FROM one WHERE a=10) 
       UPDATE one SET b = 200 WHERE a=10
    ELSE 
       INSERT INTO one VALUES (5,500);
```

Try this Alasql example [in jsFiddle](http://jsfiddle.net/agershun/8mobrL3o/1/).