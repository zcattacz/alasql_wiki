## CREATE TABLE

```js
    alasql('CREATE TABLE star (  \
                one INT DEFAULT 100, \
                two STRING,\
                three BOOL PRIMARY KEY); \
    ');
    alasql('CREATE TABLE flight (flightNo INT, fromCity STRING, toCity STRING)');
```

For tables with unknown columns skip column definition part:
```js
    alasql('CREATE TABLE mydata');
```