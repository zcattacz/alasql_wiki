# How to traverse a complex JSON doc with javascript and extract named values?

Source: http://stackoverflow.com/questions/29966520/how-do-i-traverse-a-complex-json-doc-with-javascript-and-extract-named-values

### Question
<blockquote>
It has a specific problem to solve, extracting a named value from Json, I need some javascript to traverse reasonably complex json with nested objects and arrays, and extract values. Example json is
</blockquote>

```js
  var data = {
  "query": {
      "filtered": {
          "query": {
              "match_all": {}
          },
          "filter": {
              "and": {
                  "filters": [
                      {
                          "terms": {
                              "ACCOUNT_NUMBER": [
                                  "37846589",
                                  "37846540"
                              ]
                          }
                      }
                  ]
              }
          }
      }
    }
  };
```

### Answer

You can do it with AlaSQL [SEARCH](Search) operator:
```js
    var res = alasql('SEARCH /+ACCOUNT_NUMBER/ FROM ?', [data]);
```
