# SQLite

Now Alasql can work with SQLite's [SQL.js](https://github.com/kripken/sql.js/) JavScript library together. You need to include sql.jl into the project, and attach it to Alasql like in the example below:

```html
    <script src="alasql.js"></script>
    <script src="sql.js"></script>
    <script>
        alasql('ATTACH SQLITE DATABASE Chinook("Chinook_Sqlite.sqlite");\
            USE Chinook; \
            SELECT * FROM Genre',[],function(res){
                console.log("Genres:",res.pop());
        });
    </script>
```

You can use this feature for advanced [ETL](Etl) operations. For example, you can easily open [SQLite](Sqlite) file and store it to [IndexedDB](IndexedDB) database:
```js
    alasql('ATTACH SQLITE DATABASE geo("geo.sqlite") AS geo1; \
               ATTACH INDEXEDDB DATABASE geo AS geo2; \
              SELECT * INTO geo2.cities FROM geo1.cities",[]);
``` 