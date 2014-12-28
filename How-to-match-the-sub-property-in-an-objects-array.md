# How to match the sub property in an objects array?

Source: [StackOverflow.com](http://stackoverflow.com/questions/15222493/pick-method-to-match-the-sub-property-in-an-objects-array/27659798#27659798)

### Question

Suppose there is an array of strings which are nothing but property names I want to get from each object in array of objects
```js
    var wantedPropArray=["prop1","prop2","prop3.name"];
```
Below is the objects array
```js
    var objectArray = [
            {"prop1":"prop1Data1","prop2":"prop2Data1","prop3":{"name":"Tom","age":"24","class":"graduate"},"prop4":"prop4Data1","prop5":"prop5Data1"},
            {"prop1":"prop1Data2","prop2":"prop2Data2","prop3":{"name":"Cat","age":"24","class":"graduate"},"prop4":"prop4Data2","prop5":"prop5Data2"}
            {"prop1":"prop1Data3","prop2":"prop2Data3","prop3":{"name":"Tom","age":"24","class":"graduate"},"prop4":"prop4Data3","prop5":"prop5Data3"}
            {"prop1":"prop1Data4","prop2":"prop2Data4","prop3":{"name":"Tom","age":"24","class":"graduate"},"prop4":"prop4Data4","prop5":"prop5Data4"}
        ]
    for( var item in objectArray ){			 
        var objectArrayOnlySelectedProperties = _.pick(objectArray[item] , wantedPropArray);
    }
```

Suppose for first iteration lets see objectArrayOnlySelectedProperties  data, I am expecting it to give me the result something like this
```js
    objectArrayOnlySelectedProperties = {"prop1":"prop1Data1","prop2":"prop2Data1","prop3.name":"Tom"};
```
How to create pick() method to match the sub properties of each object in an array?

### Answer

Below you can see and test a function, which construct a query to the array of nested objects. It supports nested arrays with depth more than 2:
```js
    function alaPluck(data, props) {
         var sel = props.map(function(p){
             return p.replace(/[\.]/g,'->')+' AS ['+p+']';
         }).join(',');
         return alasql('SELECT '+sel+' FROM ?',[data]);
    }
```
Try this example [at jsFiddle](http://jsfiddle.net/agershun/cLgazn79/1/)