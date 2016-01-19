# How to SUM and GROUP BY of JSON data?

Source: [StackOverflow.com](http://stackoverflow.com/questions/11199653/javascript-sum-and-group-by-of-json-data/27637293#27637293)

### Question
Some server-side code actually generates a JSON formatted string, which converts to JSON object:
```js
    var dataString=[ 
      { "category" : "Search Engines", "hits" : 5, "bytes" : 50189 },
      { "category" : "Content Server", "hits" : 1, "bytes" : 17308 },
      { "category" : "Content Server", "hits" : 1, "bytes" : 47412 },
      { "category" : "Search Engines", "hits" : 1, "bytes" : 7601 },
      { "category" : "Business", "hits" : 1, "bytes" : 2847 },
      { "category" : "Content Server", "hits" : 1, "bytes" : 24210 },
      { "category" : "Internet Services", "hits" : 1, "bytes" : 3690 },
      { "category" : "Search Engines", "hits" : 6, "bytes" : 613036 },
      { "category" : "Search Engines", "hits" : 1, "bytes" : 2858 } 
    ];
```

I need to the equivalent of an SQL statement like this:
```sql
    SELECT category, sum(hits), sum(bytes) 
    FROM dataObject
    GROUP BY category
    ORDER BY sum(bytes) DESC
```

The desired output would be an object like this:
```js
    var aggregatedObject=[ 
        { "category" : "Search Engines", "hits" : 13, "bytes" : 673684 },
        { "category" : "Content Server", "hits" : 3, "bytes" : 88930 },
        { "category" : "Internet Services", "hits" : 1, "bytes" : 3690 },
        { "category" : "Business", "hits" : 1, "bytes" : 2847 } 
    ]';
```

### Answer
This is an example with SQL query from your question:
```js
    var data = [ { "category" : "Search Engines", "hits" : 5, "bytes" : 50189 },...;

    var res = alasql('SELECT category, sum(hits) AS hits, sum(bytes) as bytes \
       FROM ? \
       GROUP BY category \
       ORDER BY bytes DESC',[data]);
```
Try this example [at jsFiddle](http://jsfiddle.net/agershun/L8471bnk/1/).

