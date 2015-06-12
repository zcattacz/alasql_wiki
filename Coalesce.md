# Keyword `COALESCE`

Show first NON NULL and non-NaN parameter:

```js
    SELECT CAST(COALESCE(hourly_wage * 40 * 52, 
        salary, 
        commission * num_sales) AS money) AS [Total Salary]
    FROM wages
    ORDER BY [Total Salary];
```

See the working example [in jsFiddle](http://jsfiddle.net/agershun/xzawkr9v/2/).