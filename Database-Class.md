# Database Class

var db = new alasql.Database(‘mydb’)
* db.databaseid – database name
* db.tables – list of tables
* db.engineid – engine (Local Storage, IndexedDB, etc.)
* db.exec(sql) – execute sql in mydb database
