# Keyword `ROLLUP`

Syntax:
```sql
    SELECT ... GROUP BY ROLLUP(column)
```

AlaSQL supports ROLLUP() grouping options:
```js
var testData = [
    { Phase: "Phase 1", Step: "Step 1", Task: "Task 1", Val: 5 },
    { Phase: "Phase 1", Step: "Step 2", Task: "Task 2", Val: 20 },
    { Phase: "Phase 2", Step: "Step 1", Task: "Task 1", Val: 25 },
    { Phase: "Phase 2", Step: "Step 2", Task: "Task 2", Val: 40 }
];

res = alasql('SELECT Phase, Step, SUM(Val) AS Val FROM ? \
                  GROUP BY ROLLUP(Phase,Step)', [testData]);
```

Try this example [in jsFiddle](http://jsfiddle.net/agershun/1nccgs6n/2/)