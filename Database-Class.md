# Database Class

Example:

    var db = new alasql.Database(‘mydb’) 

Now
* `db.databaseid` is database name
* `db.tables` array of tables
* `db.engineid` name of engine (Local Storage, IndexedDB, etc.)
* `db.exec(sql)` executes SQL statements against the mydb database
