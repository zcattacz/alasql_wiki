# How to use aggregate functions using node js?

Source: [StackOverflow.com](http://stackoverflow.com/questions/18299018/how-to-use-aggregate-functions-using-node-js/27656966#27656966)

### Question

There is a json which has the array called as chargeamountunitLevel. I want to sum-up the chargeAmount by grouping by the chargeAmountUnit. The Input json: 

```js
     "chargeamountunitLevel": [
            {
                "chargeAmount": 4,
                "chargeAmountUnit": "per hour",
                "currencyCode": "USD"
            },
            {
                "chargeAmount": 50,
                "chargeAmountUnit": "per hour",
                "currencyCode": "USD"
            },
            {
                 "chargeAmount": 25,
                 "chargeAmountUnit": "per month",
                 "currencyCode": "USD"
            },
            {
                 "chargeAmount": 25,
                 "chargeAmountUnit": "per month",
                 "currencyCode": "USD"
            }

        ]
```
The result might be as follows:
```js
        "chargeamountunitLevel": [
            {
                "chargeAmount": 54,
                "chargeAmountUnit": "per hour",
                "currencyCode": "USD"
            },
            {
                 "chargeAmount": 50,
                 "chargeAmountUnit": "per month",
                 "currencyCode": "USD"
            }

            ]
```

### Answer

You can group and aggregate data with [Alasql Node.js module](https://www.npmjs.com/package/alasql). It works in browser and Node.js.
```js
    var alasql = require('alasql');

    var res = alasql('SELECT SUM(chargeAmount) AS chargeAmount, chargeAmountUnit, currencyCode \
           FROM ? GROUP BY chargeAmountUnit, currencyCode',[chargeamountunitLevel ]);
```
You can try this example (in browser version) [in jsFiddle.](http://jsfiddle.net/agershun/jkxvc615/1/)

To install [Alasql npm package][3] use:
```
    npm install alasql
```
