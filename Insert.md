# INSERT

[INSERT VALUES](Insert Values)
```js
    alasql('INSERT INTO city (name, population) VALUES (“Moscow”,11500000), (“Kyiv”,5000000)');
    alasql('INSERT INTO city VALUES (“Paris”,3500000)');
    alasql('INSERT INTO city VALUES {name:”Berlin”, population:4000000}');
```

[INSERT DEFAULT VALUES](Insert Default Values)
```js
    alasql('INSERT INTO city DEFAULT VALUES');
```

[INSERT SELECT](Insert Select) (equivalent of SELECT INTO)
```js
    alasql('INSERT INTO city SELECT capital AS name FROM country GROUP BY capital;');
```