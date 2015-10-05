# How to run SQL script from text file?

### Question
I have all my SQL statements in text file. How to run it in AlaSQL?

### Answer
You can use SOURCE statement:
```js
    alasql('SOURCE "myfile.sql"');
```

Please not that accessing files in a browser should be done async to give the best user experience: 
```js
    alasql('SOURCE "myfile.sql"',[],function(res,err){...});
```