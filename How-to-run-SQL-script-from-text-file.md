# How to run SQL script from text file?

### Question
I have all my SQL statements in text file. How to run it in Alasql?

### Answer
You can use SOURCE statement:
```js
    alasql('SOURCE "myfile.sql"');
```