# How to count total with two criteria?

Source: [StackOverflow.com](http://stackoverflow.com/questions/25677207/count-total-with-two-criterias-using-lodash/27634849#27634849)

### Question

How to count the total devices based on location and unique serial number.
```js
    {
    "dates": [
        {
            "date": "Sep 1, 2014",
            "devices": [
                {
                    "model": "Canon",
                    "location": "Chicago",
                    "serialNum": "abc123"
                },
                {
                    "model": "Canon",
                    "location": "Chicago",
                    "serialNum": "xyz456"
                },
                {
                    "model": "HP",
                    "location": "New York",
                    "serialNum": "123456"
                },
                {
                    "model": "Brother",
                    "location": "Chicago",
                    "serialNum": "DEF777"
                }
            ]
        },
        {
            "date": "Sep 2, 2014",
            "devices": [
                {
                    "model": "Canon",
                    "location": "Chicago",
                    "serialNum": "abc123"
                },
                {
                    "model": "Canon",
                    "location": "Chicago",
                    "serialNum": "xyz456"
                }
            ]
        },
        {
            "date": "Sep 3, 2014",
            "devices": [
                {
                    "model": "Canon",
                    "location": "Chicago",
                    "serialNum": "xyz456"
                },
                {
                    "model": "Canon",
                    "location": "Chicago",
                    "serialNum": "stu789"
                },
                {
                    "model": "Epson",
                    "location": "NewYork",
                    "serialNum": "123456"
                },
                {
                    "model": "Epson",
                    "location": "NewYork",
                    "serialNum": "555555"
                },
                {
                    "model": "HP",
                    "location": "NewYork",
                    "serialNum": "987654"
                }
            ]
        }
    ]
}
```
I would like to capture the total number of unique devices per location
    Chicago - 4
    New York - 3

### Answer
```js
    var data = {...};

    // User-defined aggregator to concat arrays
    alasql.aggr.CONCAT = function(v,s) {
        return (s||[]).concat(v);
    };

    var res = alasql('SELECT location, COUNT(model) AS qty FROM \
                         (SELECT location, model FROM \
                             (SELECT VALUE CONCAT(devices) FROM ?) \
                         GROUP BY location, model) \
                      GROUP BY location',[data.dates]);
```
Try this example [at jsFiddle][2].


  [1]: http://github.com/agershun/alasql
  [2]: http://jsfiddle.net/agershun/mwaL9zeb/2/
