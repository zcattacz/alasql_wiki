# Getting Started

#### Sample 1: advanced JavaScript data processing

Group JavaScript array by field and count number of records in each group:

```js
    var data = [{a:1,b:1,c:1},{a:1,b:2,c:1},{a:1,b:3,c:1}, {a:2,b:1,c:1}];
    var res = alasql('SELECT a, COUNT(*) AS b FROM ? GROUP BY a',[data]);
    console.log(res);
```

#### Sample 2: work with IndexedDB database with SQL 

Attach IndexedDB database, and then complex query on two joined tables and filtering:
 
```js
    alasql(’ATTACH INDEXEDDB DATABASE MyBase; \ 
            USE MyBase; \
            SELECT City.* \
                   FROM City \
                   JOIN Country USING CountryCode \
                   WHERE Country.Continent = ”Asia”’, [], function (res) {
              console.log(res.pop());
    }); 
