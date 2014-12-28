# How to group javascript object grouped by multiple attributes?

Source: [StackOverflow.com](http://stackoverflow.com/questions/26408944/javascript-object-grouped-by-multiple-attributes-using-js/27617814#27617814)

### Question

There is aJavaScript object. I want to have a method to dynamically generate an object grouped by one or more attributes. The parameter `attrs` is an array, which contains some attributes for grouping.
```js
    var input= [
		{fistname:'Joe', age:'10', sex:'boy', class:'3'},
		{fistname:'Tom', age:'11', sex:'boy', class:'3'},
		{fistname:'Amily', age:'10', sex:'girl', class:'3'},
		{fistname:'Bob', age:'11', sex:'boy',class:'4'},
		{fistname:'Susan', age:'12', sex:'girl', class:'4'}
	]

    var attrs = ['age', 'class'];

    function json2group(input, attrs){...}
```
Desired result:
```js    
    [
   		{
   			label:'10',
   			groups:[
   				{
   					label:'3',
   					groups:[
   						{fistname:'Joe', age:'10', sex:'boy', class:'3'},
   						{fistname:'Amily', age:'10', sex:'girl', class:'3'}
   					]
   				}
   			]
   		},
   		{
   			label:'11',
   			groups:[
   				{
   					label:'3',
   					groups:[
   						{fistname:'Tom', age:'11', sex:'boy', class:'3'}
   					]
   				},
   				{
   					label:'4',
   					groups:[
   						{fistname:'Bob', age:'11', sex:'boy',class:'4'}
   					]
   				}
   			]
   		},
   		{
   			label:'12',
   			groups:[
   				{
   					label:'4',
   					groups:[
   						{fistname:'Susan', age:'12', sex:'girl', class:'4'}
   					]
   				}
   			]
   		}
   	]
```

### Answer

You can use Alasql library to prepare your complex structure.

This is an example with two attributes:

    var input= [ {fistname:'Joe', age:'10', sex:'boy', class:'3'},
                 {fistname:'Tom', age:'11', sex:'boy', class:'3'} ];

    function json2group(input, attr){
        var res1 = alasql('SELECT '+attr[0]+' AS label0,'+attr[1]+' AS label1, \
             ARRAY({label:'+attr[0]+',groups:_}) AS groups1 FROM ? GROUP BY label0,label1',[input]);
        return alasql('SELECT label0 AS label, ARRAY({label:label1,groups:groups1}) \
             AS groups FROM ? GROUP BY label', [res1]);
    };

    var res = json2group(input, ["age","class"]);

You can try it [in jsFiddle](http://jsfiddle.net/agershun/ztc32a8h/4/)