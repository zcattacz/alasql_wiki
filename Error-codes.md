# Error codes

To save space in the min version the debug information is spit out as the following error codes:

Error code | Meaning
-----------|---------
e00001| Unknown string in FROM clause

e01501|You can remove files only in Node.js and Apache Cordova
e01502|You can use exists() only in Node.js or Apache Cordova



e07401-tableid | Table tableid does not exists
e09301|Connot create SQLITE database in memory. Please attach it.
e09302|It not supported to drop SQLite database. Please detach it.
e09303-dbid|Unable to attach database as dbid because it already exists
e09304-path|Cannot open SQLite database file path
e09305|Cannot attach SQLite database without a file
e09401|Cannot create new database file, because it already exists
e09402|Cannot drop database file, because it does not exist
e09403-dbid|Unable to attach database as dbid because it already exists
e09404|Data in FileStorage database are corrupted
e09405-tableid-fsdbid|Table tableid alsready exists in the database fsdbid
e09406-tableid|Cannot drop table tableid in fileStorage, because it does not exist