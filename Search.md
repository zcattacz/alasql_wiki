# SEARCH

AlaSQL ```SEARCH``` operator is designed to traverse over JSON objects and graphs.

Syntax:
```sql
    SEARCH selectors [FROM (table|object)]
```
You can use it with graphs:
```js
    var res = alasql('SEARCH / "Harry" PATH("Roger") VERTEX name');
```
or with JSON files:
```js
   var catalog = { 
     Europe: {
       fruits: [
         {fruit:'Apple'},
         {fruit:'Peach'},          
       ]
     },
     Asia: {
         fruit:'Pineapple'          
     },
     Africa: {
         fruit:'Banana'          
     }
   };

    var res = alasql('SEARCH Europe FROM ?',[catalog]);
    // [{fruits: [
    //    {fruit:'Apple'},
    //    {fruit:'Peach'},          
    //  ]}]);

    var res = alasql('SEARCH /fruits/ FROM ?',[catalog]);
    // [{fruit:'Apple'}, {fruit:'Peach'}]

    var res = alasql('SEARCH /fruits/fruit FROM ?',[catalog]);
    // ['Apple','Peach']

    var res = alasql('SEARCH /fruits/WHERE(fruit="Apple") FROM ?',[catalog]);
    // [{fruit:'Apple'}]

    var res = alasql('SEARCH ///WHERE(fruit="Apple") FROM ?',[catalog]);
    // [{fruit:'Apple'}]
```

See also: [SELECT](Select)