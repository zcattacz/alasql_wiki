## AlaSQL + Meteor

AlaSQL supports querieng directly on Meteor collections. 

Sounds simple - And it is. [Walker-Morgan](https://www.compose.io/articles/author/dj/) from [compose.io](https://www.compose.io/articles/meteor-sql-and-other-databases/) puts it this way:


>This lets you turn
>
    return Robots.find({}, { sort: { introduced: 1 }} ); 
>     
>into
>
    return alasql('SELECT * FROM ? ORDER BY introduced',[Robots]);  
>
>which doesn't look like a huge jump, until you realise that this works in both the browser and the server and opens up a way to do JOIN, GROUP BY, UNION, DISTINCT and others.

Read [the rest of the article about Meteor and AlaSQL](https://www.compose.io/articles/meteor-sql-and-other-databases/) if it looks useful to you. 

----

AlaSQL works on client and the server side. 

To get started import AlaSQL from NPM in your code

```
import alasql from 'alasql';
```

Now you can query directly on Meteor Collections with the `alasql` function: 

```js
    Template.body.helpers({
       tasks: function () {
         return alasql('SELECT * WHEERE done = false FROM ?',[Tasks]);
       }
    });
```

You can use it with find() options with the METEOR() from-function:
```
    return alasql('SELECT * FROM ?',[Tasks]);
    return alasql('SELECT * FROM METEOR(?)',[Tasks]);
    return alasql('SELECT * FROM METEOR(?,?)',[Tasks,{text:"Hello world!"}]);
    return alasql('SELECT * FROM METEOR(?,{text:"Hello world!"})',[Tasks]);
```