# Keyword `WITH` 

In AlaSQL you can use WITH caluse with SELECT operator to create temporary tables for current select 
(a.k.a. Commom Table Expressions). 

<blockquote>
A common table expression (CTE) can be thought of as a temporary result set that is defined within the execution scope of a single SELECT, INSERT, UPDATE, DELETE, or CREATE VIEW statement. A CTE is similar to a derived table in that it is not stored as an object and lasts only for the duration of the query. CTE can be referenced multiple times in the same query.
</blockquote>

[Source](https://technet.microsoft.com/en-us/library/ms190766(v=sql.105).aspx)

In current version of AlaSQL CTE canot be self-referencing. 

```sql
 With Totals as
 (
    select  *,
            price * quantity as [Total price]
    from    grocery
 )
 select  *
    ,  case
         when [Total price]>100 and [Total price]<= 200 then '2%'
         when [Total price]>200 and [Total price]<= 300 then '3%'
         when [Total price]>300 and [Total price]<= 400 then '4%'
        else '0%'
     end as tax
 
 from
   Totals
```

You can try this example [in jsFiddle](http://jsfiddle.net/n131zmw9/2/).

```js
    var res = alasql('WITH one AS (SELECT * FROM ?),\
                           two AS (SELECT * FROM ?)\
                      SELECT * FROM one,two', [[{a:1},{a:2}],[{b:10},{b:20}]]);
```
You can try this example [in jsFiddle](http://jsfiddle.net/agershun/k0e8hc60/1/).
