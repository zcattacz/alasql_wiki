# Keyword `GRAPH`

_Keyword for graph-related commands._

AlaSQL is a multi-paradigm database with support for both documents and graphs. Below you can find an example
how to create graph:

```js
    alasql('CREATE GRAPH #Olga, #Helen, #Pablo, #Andrey, #Alice, \
        #Olga >> #Pablo, #Helen >> #Andrey, \
        #Pablo >> #Alice, #Andrey >> #Alice');
```

Search over it with `SEARCH` operator:

```js
    // Whom loves Olga?
    alasql('SEARCH / #Olga >> name');
    // ['Pablo']

    // Whom loves Olga's love objects?
    alasql('SEARCH / #Olga >> >> name');
    // ['Alice']

    // Who loves lovers of Alice?
    alasql('SEARCH / ANY(>> >> #Alice) name');
    // ['Olga','Helen']

```

You also make searches over JSON object with SEARCH operator:

```js
    var data = {a:{a:{a:{a:{b:10}}}},b:20};
    var res = alasql('SEARCH a b FROM ?',[data]);
    var res = alasql('SEARCH (a)+ b FROM ?',[data]);
    var res = alasql('SEARCH (a a)+ b FROM ?',[data]);
    var res = alasql('SEARCH (a a a)+ b FROM ?',[data]);
    var res = alasql('SEARCH (/)+ b FROM ?',[data]);
    var res = alasql('SEARCH /+b FROM ?',[data]);
    var res = alasql('SEARCH a* b FROM ?',[data]);
    var res = alasql('SEARCH a+ b FROM ?',[data]);
    var res = alasql('SEARCH a? b WHERE(b>20) FROM ?',[data]);
```


Another example:

```javascript
    var res = alasql('CREATE GRAPH Pablo, Maxim, Alex, Napoleon, \
      Josephine,  Kate, Julia  {age:27}, Paloma, \
      #Pablo >loves> #Julia, #Maxim >> #Julia, #Alex >> #Kate, \
      #Kate >> #Julia, #Alex >> #Paloma, #Napoleon > "loves" > #Josephine, \
      #Josephine >"knows"> #Pablo');

    var res = alasql('SEARCH PATH(#Pablo) name FROM #Napoleon ');
    // returns ['loves','Josephine','knows','Pablo']
```
You can play with graphs in AlaSQL in [this jsFiddle example](http://jsfiddle.net/fgzya692/2/).


Please see more examples in test300 - test309


