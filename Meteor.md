## AlaSQL + Meteor

AlaSQL supports querieng directly on Meteor collections. 

Sounds simple - And it is. Walker-Morgan from compose.io puts it this way:


>This lets you turn
>
    return Robots.find({}, { sort: { introduced: 1 }} ); 
>     
>into
>
    return alasql('SELECT * FROM ? ORDER BY introduced',[Robots]);  
>
>which doesn't look like a huge jump, until you realise that this works in both the browser and the server and opens up a way to do JOIN, GROUP BY, UNION, DISTINCT and others.

Please read [his article about Meteor and AlaSQL](https://www.compose.io/articles/meteor-sql-and-other-databases/) if you find it interesting. 

----

AlaSQL works on client and the server side. To get started install AlaSQL for Meteor from [the Meteor packagemanager aatmospherejs](https://atmospherejs.com/agershun/alasql):

```
    meteor add agershun:alasql
```

Now you can query directly on Meteor Collections with the `alasql` function: 

```js
    Template.body.helpers({
       tasks: function () {
         return alasql('SELECT * WHEERE done = false FROM ?',[Tasks]);
       }
    });
```
