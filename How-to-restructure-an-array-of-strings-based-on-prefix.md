#How to restructure an array of strings based on prefix?

Source: [StackOverflow](http://stackoverflow.com/questions/34895800)

### Question
I have an array containing a list of filenames:
```js
    var files = ['home_01.ai','home_02.ai','home_03.ai','imprint_01.ai','imprint_02.ai']
```
What I want to do is reorganise this array into a multi-dimensional array that groups together each file with the same prefix. In this case:
```js
    var firstArray = ['home_01.ai','home_02.ai','home_03.ai'], /*home*/
    secondArray = ['imprint_01.ai','imprint_02.ai']; /*imprint*/
```
How could I achieve that when there can be a variable amount of prefixes that can be any length in my file array?

### Answer

You can do it with AlaSQL JavaScript data processing library.

Here is the solution for your problem:
```js
    var res = alasql('COLUMN OF SELECT ARRAY(_) FROM ? \
         GROUP BY _->split("_")->0',[files]);
```
This statement returns array of arrays grouped by prefix:
```
    [ [ 'home_01.ai', 'home_02.ai', 'home_03.ai' ],
      [ 'imprint_01.ai', 'imprint_02.ai' ] ]
```
Here:

* COLUMN OF - return only first column of query
* SELECT ... FROM ? GROUP BY ... - select statement
* ARRAY(_) - group records in array
* FROM ? - query from parameter [files]
* GROUP BY _->split("_")->0 - take a value, split it with '_' and then take first element of array (similar to JS r.split('_')[0]
