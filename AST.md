### SQL to JavaScript parser and compiler

You can use AlaSQL to parse to AST and compile SQL statements:

```js
    // Parse to AST
    var ast = alasql.parse("SELECT * FROM one");
    console.log(ast.toString()); // Print restored SQL statement

    // Compile to JavaScript function with or without parameters
    var statement = alasql.compile("SELECT * FROM one WHERE a > ? AND b < ?");
    statement([1,5]);
```

AlaSQL uses wonderful [Jison](http://jison.org) parser to produce AST-tree.
