
You can search graph data with SEARCH operator:

```javascript
    var res = alasql('CREATE GRAPH Pablo, Maxim, Alex, Napoleon, \
      Josephine,  Kate, Julia  {age:27}, Paloma, \
      #Pablo >loves> #Julia, #Maxim >> #Julia, #Alex >> #Kate, \
      #Kate >> #Julia, #Alex >> #Paloma, #Napoleon > "loves" > #Josephine, \
      #Josephine >"knows"> #Pablo');

    var res = alasql('SEARCH PATH(#Pablo) name FROM #Napoleon ');
    // returns ['loves','Josephine','knows','Pablo']
```
You can play with grpahs in AlaSQL in [this jsFiddle example](http://jsfiddle.net/fgzya692/2/).
