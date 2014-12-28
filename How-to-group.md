# How to group?

Source: [StackOverflow.com](http://stackoverflow.com/questions/17346417/groupby-and-linq-node-js/27647975#27647975)

### Question

For example I have this data :
```js
    {"date":"2013/06/26","name":"A","number":1}
    {"date":"2013/06/26","name":"A","number":5}
    {"date":"2013/06/27","name":"B","number":4}
    {"date":"2013/06/27","name":"A","number":4}
```
and I want write like this query but with LINQ for node js
```sql
    SELECT date, name, SUM(number)
    FROM data
    GROUPBY date, name
```

### Answer
```js
    var data = [{"date":"2013/06/26","name":"A","number":1},
                {"date":"2013/06/27","name":"A","number":4}];

    var res = alasql('SELECT [date], name, SUM(number) AS number \
                          FROM ? GROUP BY [date], name', [data]);
```
Try this example [at jsFiddle](http://jsfiddle.net/agershun/fdj25181/1/).

Comments: **[date]** field is in square brackets, because "DATE" is a reserved word for SQL.

