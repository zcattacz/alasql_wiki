# _ Underscore Object

Source: [StackOverflow](http://stackoverflow.com/questions/34856054/alasql-how-to-reference-the-json-object-it-self-to-call-a-function-on-it/34863069#34863069)
### Question: How to reference the JSON object it self (to call a function on it)?

I have the following object and I would like to call it's function.
```
[{a:1, fn:function(){} }]
```
Now I know if the object would be nested (```[{a:1, b:{fn:function(){} } }]```) that I could do ```b->fn()``` but how do I do it when it's direct property of the first element?

### Answer
Please use _ variable. This is a pseudo-variable, which includes the record whole itself:
```sql
SELECT _->fn() FROM ...
```
Here is the example:
```js
var data = [
  {a:1, fn:function(){return 10}},
  {a:2, fn:function(){return 20}},
]

var res = alasql('SELECT _->fn() AS b FROM ?',[data]);
```
will returs:
```
[{"b":10},{"b":20}]
```
You can play with it [in jsFiddle](http://jsfiddle.net/agershun/ws0vewj0/5/)

