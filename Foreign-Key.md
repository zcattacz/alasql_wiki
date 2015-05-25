# FOREIGN KEY

AlaSQL suports FOREIGN KEY concept.

In this example field ```Orders.fruitid``` reference to ```Fruits``` table:
```sql
     CREATE DATABASE Fruits;
      USE DATABASE Fruits;
      CREATE TABLE Fruits (
        fruitid INT PRIMARY KEY,
        fruitname NVARCHAR(MAX),
        price MONEY
      );

      CREATE TABLE Orders (
        orderid INT PRIMARY KEY IDENTITY,
        fruitid INT REFERENCES Fruits(fruitid),
        qty FLOAT
      );
```