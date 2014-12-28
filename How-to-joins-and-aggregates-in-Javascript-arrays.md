# How to joins and aggregates in Javascript arrays?

Source: [StackOverflow.com](http://stackoverflow.com/questions/15043921/joins-and-aggregates-in-javascript-arrays/27628099#27628099)

### Question

I have been trying for hours to do this using json.js but is just too much for something that seems simple. I have this example data:
```js
    var hotels = [
        { id: 101, Name: "Hotel 101", WebFacilities: [8, 9, 10] },
        { id: 102, Name: "Hotel 101", WebFacilities: [8] },
        { id: 103, Name: "Hotel 101", WebFacilities: [8, 10] }
    ];

    var facilities = [
        { id: 8, Name: "Facility 8" },
        { id: 9, Name: "Facility 9" },
        { id: 10, Name: "Facility 10" }
    ];
```
I want to get this:
```js
    var selectedFacilities = [
        { id: 8, Name: "Facility 8", Count: 3 },
        { id: 9, Name: "Facility 9", Count: 1 },
        { id: 10, Name: "Facility 10", Count: 2 }
    ]
```
How do I do this?

### Answer
```js
     var res = alasql('SELECT id, FIRST(Name) AS Name, COUNT(*) AS [Count] FROM ? facilities \
            JOIN ? hotels ON facilities.id IN hotels.WebFacilities \
            GROUP BY id', [facilities,hotels]);
```
Try this example [at jsFiddle](http://jsfiddle.net/agershun/aohs22s8/3/)