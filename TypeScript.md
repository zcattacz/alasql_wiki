# TypeScript

AlaSQL ```dist``` includes definition file for the library: Simply include it to your TypeScript project:

```typescript
/// <reference path="alasql.d.ts" />
var alasql = require('alasql');
```

After it TypeScript compiler will check syntax of ```alasql()``` function and options.
```
// Good test 
var res = alasql('=2*3',1,23,4,5);
// Ok

// Bad test 
alasql('=2*3',1,23,4,5);
// This combination should generate type error
```