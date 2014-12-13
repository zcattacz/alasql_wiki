## INSERT DEFAULT VALUES
```js
   alasql('CREATE TABLE Orders (OrderNo INT DEFAULT 1, Desc STRING DEFAULT "Something")');
   alasql('INSERT INTO Orders DEFAULT VALUES');
```