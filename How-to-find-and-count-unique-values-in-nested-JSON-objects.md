# How to find and count unique values in nested JSON objects?

Source: [StackOverflow.com](http://stackoverflow.com/questions/27651708/how-do-i-find-and-count-unique-values-in-nested-json-objects/27656790#27656790)

### Question

There is the following JavaScript object:
```js
    {
      "business": [
    {
      "order_contents": [
        {
          "id": 83,
          "name": "product 1",
          "price": "1.99",
          "quantity": 1,
          "total": "1.99",
          "ingredients": [],
          "extras": []
        },
        {
          "id": 83,
          "name": "product 1",
          "price": "1.99",
          "quantity": 1,
          "total": "1.99",
          "ingredients": [],
          "extras": []
        },
        {
          "id": 83,
          "name": "product 1",
          "price": "1.99",
          "quantity": 1,
          "total": "1.99",
          "ingredients": [],
          "extras": []
        },
        {
          "id": 85,
          "name": "product 3",
          "price": "1.99",
          "quantity": 1,
          "total": "1.99",
          "ingredients": [],
          "extras": []
        },
        {
          "id": 83,
          "name": "product 1",
          "price": "1.99",
          "quantity": 1,
          "total": "1.99",
          "ingredients": [],
          "extras": []
        },
        {
          "id": 84,
          "name": "product 2",
          "price": "1.99",
          "quantity": 1,
          "total": "1.99",
          "ingredients": [],
          "extras": []
        },
        {
          "id": 83,
          "name": "product 1",
          "price": "1.99",
          "quantity": 1,
          "total": "1.99",
          "ingredients": [],
          "extras": []
        },
        {
          "id": 83,
          "name": "product 1",
          "price": "1.99",
          "quantity": 1,
          "total": "1.99",
          "ingredients": [],
          "extras": []
        },
        {
          "id": 83,
          "name": "product 1",
          "price": "1.99",
          "quantity": 1,
          "total": "1.99",
          "ingredients": [],
          "extras": []
        },
        {
          "id": 83,
          "name": "product 1",
          "price": "1.99",
          "quantity": 1,
          "total": "1.99",
          "ingredients": [],
          "extras": []
        },
        {
          "id": 83,
          "name": "product 1",
          "price": "1.99",
          "quantity": 1,
          "total": "1.99",
          "ingredients": [],
          "extras": []
        },
        {
          "id": 83,
          "name": "product 1",
          "price": "1.99",
          "quantity": 1,
          "total": "1.99",
          "ingredients": [],
          "extras": []
        },
        {
          "id": 84,
          "name": "product 2",
          "price": "1.99",
          "quantity": 1,
          "total": "1.99",
          "ingredients": [],
          "extras": []
        }
       ]
      }
     ]
    }
```
What i am trying to accomplish is when the order comes through a function scans the JSON and creates an array with each unique product name and adds 1 to the quantity each time.

### Answer

You can group and aggregate arrays with the following code:
```js
    var data = {"business": [...]};

    var res1 = alasql('SELECT id, FIRST(name) AS name, COUNT(*) AS cnt FROM ? GROUP BY id',
                     [data.business[0].order_contents]);
```
Try the example [in jsFiddle](http://jsfiddle.net/agershun/11gd86nx/5/).

Or for output like: {"product 1":10, "product 2": 23} you can use the following query:
```js
    var res2 = alasql('SELECT INDEX name, COUNT(*) AS cnt FROM ? GROUP BY name'.
                      [data.business[0].order_contents]);
```
