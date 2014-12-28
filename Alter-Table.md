# ALTER TABLE

ADD COLUMN
```js
    alasql('ALTER TABLE City ADD COLUMN Continent STRING');
```
RENAME COLUMN
```js
    alasql('ALTER TABLE City RENAME COLUMN Continent TO WorldPart');
```
DROP COLUMN
```js
    alasql('ALTER TABLE City DROP COLUMN Continent');
```
RENAME TO
```ja
   alasql('ALTER TABLE City RENAME TO Capital');
```
