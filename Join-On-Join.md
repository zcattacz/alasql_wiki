#JOIN ON JOIN

This page created for understanding results produced with combination of joins.

## Create script
First we will create three tables and fill them with values:
```sql
CREATE TABLE one (id NVARCHAR(3));
CREATE TABLE two (id NVARCHAR(3));
CREATE TABLE three (id NVARCHAR(3));

INSERT INTO one VALUES ('A'),('AB'),('AC'),('ABC');
INSERT INTO two VALUES ('B'),('AB'),('BC'),('ABC');
INSERT INTO three VALUES ('C'),('BC'),('AC'),('ABC');
```

## 1. INNER

### 1.1. INNER AND INNER
```sql
SELECT one.id AS a, two.id AS b FROM one INNER JOIN two ON one.id = two.id INNER JOIN three ON two.id = three.id;
```
returns
```
ABC	ABC	ABC
```
### 1.2. INNER AND LEFT
```sql
SELECT one.id AS a, two.id AS b, three.id AS c FROM one INNER JOIN two ON one.id = two.id LEFT OUTER JOIN three ON two.id = three.id;
```
returns:
```
AB	AB	NULL
ABC	ABC	ABC
```
### 1.3. INNER AND RIGHT
```sql
SELECT one.id AS a, two.id AS b, three.id AS c FROM one INNER JOIN two ON one.id = two.id RIGHT JOIN three ON two.id = three.id;
```
returns:
```
NULL	NULL	C
NULL	NULL	BC
NULL	NULL	AC
ABC	ABC	ABC
```
### 1.4. INNER AND OUTER
```sql
SELECT one.id AS a, two.id AS b, three.id AS c FROM one INNER JOIN two ON one.id = two.id FULL OUTER JOIN three ON two.id = three.id;
```
returns:
```
AB	AB	NULL
ABC	ABC	ABC
NULL	NULL	C
NULL	NULL	BC
NULL	NULL	AC
```

## 2. LEFT
### 2.1. LEFT AND INNER
```sql
SELECT one.id AS a, two.id AS b, three.id AS c FROM one LEFT JOIN two ON one.id = two.id INNER JOIN three ON two.id = three.id;
```
returns
```
ABC	ABC	ABC
```

### 2.2. LEFT AND LEFT
```sql
SELECT one.id AS a, two.id AS b, three.id AS c FROM one LEFT JOIN two ON one.id = two.id LEFT JOIN three ON two.id = three.id;
```
returns
```
A	NULL	NULL
AB	AB	NULL
AC	NULL	NULL
ABC	ABC	ABC
```

### 2.3. LEFT AND RIGHT
```sql
SELECT one.id AS a, two.id AS b, three.id AS c FROM one LEFT JOIN two ON one.id = two.id RIGHT JOIN three ON two.id = three.id;
```
returns
```
NULL	NULL	C
NULL	NULL	BC
NULL	NULL	AC
ABC	ABC	ABC
```

### 2.4. LEFT AND OUTER
```sql
SELECT one.id AS a, two.id AS b, three.id AS c FROM one LEFT JOIN two ON one.id = two.id INNER JOIN three ON two.id = three.id;
```
returns
```
A	NULL	NULL
AB	AB	NULL
AC	NULL	NULL
ABC	ABC	ABC
NULL	NULL	C
NULL	NULL	BC
NULL	NULL	AC
```

## 3. RIGHT

### 3.1. RIGHT AND INNER
```sql
SELECT one.id AS a, two.id AS b, three.id AS c FROM one RIGHT JOIN two ON one.id = two.id INNER JOIN three ON two.id = three.id;
```
returns:
```
NULL	BC	BC
ABC	ABC	ABC
```

### 3.2. RIGHT AND LEFT
```sql
SELECT one.id AS a, two.id AS b, three.id AS c FROM one RIGHT JOIN two ON one.id = two.id LEFT JOIN three ON two.id = three.id;
```
returns:
```
NULL	B	NULL
AB	AB	NULL
NULL	BC	BC
ABC	ABC	ABC
```

### 3.3. RIGHT AND RIGHT
```sql
SELECT one.id AS a, two.id AS b, three.id AS c FROM one RIGHT JOIN two ON one.id = two.id RIGHT JOIN three ON two.id = three.id;
```
returns
```
NULL	NULL	C
NULL	BC	BC
NULL	NULL	AC
ABC	ABC	ABC
```

### 3.4. RIGHT AND OUTER
```sql
SELECT one.id AS a, two.id AS b, three.id AS c FROM one RIGHT JOIN two ON one.id = two.id RIGHT JOIN three ON two.id = three.id;
```
returns
```
NULL	B	NULL
AB	AB	NULL
NULL	BC	BC
ABC	ABC	ABC
NULL	NULL	C
NULL	NULL	AC
```

## OUTER

### 4.1. OUTER AND INNER
```sql
SELECT one.id AS a, two.id AS b, three.id AS c FROM one FULL OUTER JOIN two ON one.id = two.id INNER JOIN three ON two.id = three.id;
```
returns:
```
NULL	BC	BC
ABC	ABC	ABC
```

### 4.2. OUTER AND LEFT
```sql
SELECT one.id AS a, two.id AS b, three.id AS c FROM one FULL OUTER JOIN two ON one.id = two.id LEFT JOIN three ON two.id = three.id;
```
returns:
```
A	NULL	NULL
AB	AB	NULL
AC	NULL	NULL
ABC	ABC	ABC
NULL	B	NULL
NULL	BC	BC
```

### 4.3. OUTER AND RIGHT
```sql
SELECT one.id AS a, two.id AS b, three.id AS c FROM one FULL OUTER JOIN two ON one.id = two.id RIGHT JOIN three ON two.id = three.id;
```
returns:
```
NULL	NULL	C
NULL	BC	BC
NULL	NULL	AC
ABC	ABC	ABC
```

### 4.4. OUTER AND OUTER

```sql
SELECT one.id AS a, two.id AS b, three.id AS c FROM one FULL OUTER JOIN two ON one.id = two.id FULL OUTER JOIN three ON two.id = three.id;
```
returns
```
A	NULL	NULL
AB	AB	NULL
AC	NULL	NULL
ABC	ABC	ABC
NULL	B	NULL
NULL	BC	BC
NULL	NULL	C
NULL	NULL	AC
```
