# How to recursive find and replace in multidimensional JavaScript object?

### Question 

Source: [StackOverflow](http://stackoverflow.com/questions/29473526/recursive-find-and-replace-in-multidimensional-javascript-object)

I need to find and replace values in my object when they match a regular expression (e.g. **myVar**); The object that I need to loop through is user defined and structure varies.

Here is an example object, shortened for simplicity.
```js
var testObject = {
    name: "/pricing-setups/{folderId}", 
    method: "POST", 
    endpoint: "/pricing-setups/:folderId", 
    functionName: "create",
    Consumes: null,
    filename: "apicontracts/pricingsetups/PricingSetupServiceProxy.java",
    pathParam: [
        {$$hashKey: "06S",
          key: "folderId",
          value: "**myVar**"}
    ],
    queryParam: [],
    request_payload: "{'title':'EnterAname'}",
    returnList: []
}
```
This object is passed into a master function that builds a AngularJs resource object using the passed in object.

### Answer

You can use AlaSQL [SEARCH](Search) operator.