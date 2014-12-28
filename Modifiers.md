# Return Value Modifiers
Return Value Modifiers use for modification of alasql() function output from array of objects to anothe JavaScript data structure, like array of arrays.

#### SELECT By default
Returns array of objects:
```js
    [{a:1,b:10},{a:2,b:20}]
```
#### SELECT VALUE
Returns first value of first row:
```js
    1
```
#### SELECT COLUMN
Returns first column from all rows:
```js
    [1,2]
```

#### SELECT ROW
Returns values of all columns of first row:
```
    [1,10]
```
#### SELECT MATRIX
Returns array of arrays
```
    [[1,10],[2,20]]
```

#### SELECT INDEX
Create object by key, value
```js
    alasql('SELECT INDEX a,b FROM ?', [[{a:1,b:10},{a:2,b:20}]])
    => {1:{b:10}, 2:{b:20}}
```
#### SELECT TEXT
Create text by merging values of arry and joining with '\n'.
```js
    "This is a line\nand another line"
```
## Examples
Return number of all lines in README.md
```js
    alasql('SELECT VALUE COUNT(*) FROM TXT(‘README.md’)');
```

Return array of arrays:
```js
    alasql('SELECT MATRIX * FROM one');
```
