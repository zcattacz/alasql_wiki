# How to merge object arrays based on join of a key property in each?

Source: [StackOverflow.com](http://stackoverflow.com/questions/6059084/merging-extend-javascript-object-arrays-based-on-join-of-a-key-property-in-each/27618087#27618087)

### Question

How to merge the following object arrays, by first joining on the id property?
```js
    var arr1 = [{
        id: 1,
        name: 'fred',
        title: 'boss'
    },{
        id: 2,
        name: 'jim',
        title: 'nobody'
    },{
        id: 3,
        name: 'bob',
        title: 'dancer'
    }];
    
    var arr2 = [{
        id: 1,
        wage: '300',
        rate: 'day'
    },{
        id: 2,
        wage: '10',
        rate: 'hour'
    },{
        id: 3,
        wage: '500',
        rate: 'week'
    }];
```
The result would be
```js
    [{
        id: 1,
        name: 'fred',
        title: 'boss',
        wage: '300',
        rate: 'day'
    },{
        id: 2,
        name: 'jim',
        title: 'nobody',
        wage: '10',
        rate: 'hour'
    },{
        id: 3,
        name: 'bob',
        title: 'dancer',
        wage: '500',
        rate: 'week'
    }]
```

### Answer

You can merge two arrays by id column with like in this example:
```js
    var res = alasql('SELECT * FROM ? arr1 JOIN ? arr2 USING id', [arr1,arr2]);
```
Try this example [at jsFiddle](http://jsfiddle.net/agershun/n2rn5fez/2/)