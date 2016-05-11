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

### Errors

All IndexedDB operations are asyncronous. This is the main reason ```try catch``` construction does not catch errors fron IndexedDB at the moment. 

If you need to handle errors please try the following

```js
alasql.options.errorlog = true; 
alasql('ATTACH INDEXEDDB DATABASE NN'.[].function(data,err){
    if(err) // do something with error;
});

// or 

alasql.options.errorlog = function(err){console.log(err)}; // Do something with error

alasql('ATTACH INDEXEDDB DATABASE NN'.[].function(data){
    //do something with data
});

# DROP

To [[drop]] an IndexedDB database please remember to include the engine name

```sql
DROP INDEXEDDB DATABASE db_name
```