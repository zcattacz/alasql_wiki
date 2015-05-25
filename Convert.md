# CONVERT()

AlaSQL realizes CONVERT() function:
```js
alasql('SET @d = DATE("01/08/2015 12:34:56.789"); \
            SELECT \
                CONVERT(STRING,@d,1),\
                CONVERT(STRING,@d,2),\
                CONVERT(STRING,@d,3),\
                CONVERT(STRING,@d,4),\
                CONVERT(STRING,@d,5),\
                CONVERT(STRING,@d,6),\
                CONVERT(STRING,@d,7),\
                CONVERT(STRING,@d,8),\
                CONVERT(STRING,@d,10),\
                CONVERT(STRING,@d,11),\
                CONVERT(STRING,@d,12),\
                CONVERT(STRING,@d,101),\
                CONVERT(STRING,@d,102),\
                CONVERT(STRING,@d,103),\
                CONVERT(STRING,@d,104),\
                CONVERT(STRING,@d,105),\
                CONVERT(STRING,@d,106),\
                CONVERT(STRING,@d,107),\
                CONVERT(STRING,@d,108),\
                CONVERT(STRING,@d,110),\
                CONVERT(STRING,@d,111),\
                CONVERT(STRING,@d,112)\
            ');
```
See the example [in jsFiddle](http://jsfiddle.net/agershun/qytn1n0L/)