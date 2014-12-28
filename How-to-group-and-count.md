# How to group and count?

Source: [StackOverflow.com](http://stackoverflow.com/questions/23024623/lodash-group-and-count/27634544#27634544)

### Question

There is an array like this:
```js
    [{ dep: 'A', qt: 10, price: 5},
     { dep: 'A', qt: 5,  price: 2.30 },
     { dep: 'B', qt: 3,  price: 2.20 },
     { dep: 'C', qt: 1,  price: 4 },
     { dep: 'C', qt: 4,  price: 10 }
     ...etc.. 
    ]
```
What's the elegant way to both group and sum values, resulting into:
```js
    [{ dep: 'A', qt: 15, price: 61.5 },
     { dep: 'B', qt: 3, price: 2.20 },
     { dep: 'C', qt: 5: price: 44 }
    ]
```
### Answer

You can do it in elegant way:
```js
    var res = alasql('SELECT dep, SUM(qt) AS qt, SUM(qt*price) AS amt, 
                        AGGR(amt/qt) AS price FROM ? GROUP BY dep',[data]); 
```
Try this example [at jsFiddle](http://jsfiddle.net/agershun/30to2rh8/1/).

I changed a little bit the algorithm for calculation of average price based on quantity sold.
