# How to filter an array using an array?

Source: [StackOverflow.com]()

### Question

I am trying to look at every value in one array and see if any of them are contained in any of the other array values.
```js
    arrOne = ['a', 'b' ,'c' ];
    arrTwo = ['option a', 'option c', 'option b', 'option d'];
```
So I want it to cycle through to see every value in arrTwo that has one of the values from arrOne and remove the ones that don't so I get:
```js    
    arrFinal = ['option a', 'option c', 'option b'];
```
### Answer

```js
    var res = alasql('SELECT COLUMN _ FROM ? arrTwo WHERE EXISTS( \
          SELECT _ FROM ? arrOne WHERE arrTwo._ LIKE "%"+arrOne._+"%")',
          [arrTwo, arrOne]);
```
Try this example [in jsFiddle](http://jsfiddle.net/agershun/11gd86nx/2/)