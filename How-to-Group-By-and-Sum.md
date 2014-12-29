# How to Group By and Sum?

Source: [StackOverflow.com](http://stackoverflow.com/questions/25047463/group-by-and-sum-using-underscore-lodash/27634325#27634325)

### Question

There is a JSON like this: 

    [
      {
         platformId: 1,
         payout: 15,
         numOfPeople: 4
      },
      {
         platformId: 1,
         payout: 12,
         numOfPeople: 3

      },
      {
         platformId: 2,
         payout: 6,
         numOfPeople: 5

      },
      {
         platformId: 2,
         payout: 10,
         numOfPeople: 1
      },
    
    ]


And I want to Group it by `platformId` with sum of `payout` and `numOfPeople`. I.e. in result I want JSON like this:

    [
      "1": {
         payout: 27,
         numOfPeople: 7
       },
    
      "2": {
         payout: 16,
         numOfPeople: 6
      }
    ] 

### Answer

```js
    var res = alasql('SELECT INDEX platformId, {platformId:platformId, numOfPeople:numOfPeople} \
         FROM (SELECT platformId, SUM(payout) AS payout, SUM(numOfPeople) AS numOfPeople \
             FROM ? GROUP BY platformId)',[data]);
```
Try this example [at jsFiddle](http://jsfiddle.net/agershun/x110xhfc/3/)