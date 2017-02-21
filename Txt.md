# TXT

AlaSQL can import and export data from TXT format:

Syntax:
```sql
    SELECT column INTO TXT(filename) FROM tableid;
    SELECT column FROM TXT(filename) ;
```

Please note that you can avoid letting AlaSQL try to add extension to filenames by setting `autoExt:false` in the options given. 

See also: [CSV](Csv), [TAB](Tab), [TSV](Tsv), [XLSX](Xlsx), [JSON](Json)
