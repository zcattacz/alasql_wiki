## Work with IndexedDB
Sample (try it in [jsFiddel](http://jsfiddle.net/agershun/1t2rrr78/)):
```js
    var cityData = [{city:"Redmond", population:57530},
        {city:"Atlanta",population:447841},
        {city:"San Fracisco", population:837442}];

    // Create IndexdDB database and fill it with data from array
    alasql('CREATE INDEXEDDB DATABASE IF NOT EXISTS geo;\
        ATTACH INDEXEDDB DATABASE geo; \
        USE geo; \
        DROP TABLE IF EXISTS cities; \
        CREATE TABLE cities; \
        SELECT * INTO cities FROM ?', [cityData], function(){

        // Select data from IndexedDB
        alasql('SELECT COLUMN * FROM cities WHERE population > 100000 ORDER BY city DESC',
           [],function(res){
                document.write('Big cities: ', res.join(','));
        });
    });
```