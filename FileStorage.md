# FileStorage

AlaSQL supports its own file format of database storage. This is a JSON string representing the database.

To use FileStorage you need to attach database:
```sql
    ATTACH FILESTORAGE DATABASE one("./myFile.json");
```


## DROP

To [[drop]] a FileStorage database please remember to include the engine name

```sql
DROP FILESTORAGE DATABASE db_name
```