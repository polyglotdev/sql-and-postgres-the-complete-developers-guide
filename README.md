# SQL and PostgreSQL: The Complete Developer's Guide

[SQL and PostgreSQL: The Complete Developer's Guide](https://www.udemy.com/course/sql-and-postgresql)

## What is PostgreSQL?

PostgreSQL is a powerful, open-source object-relational database system. It has
more than 15 years of active development and a proven architecture that has
earned it a strong reputation for reliability, data integrity, and correctness.


## Database Design

Database design is the organization of data according to a database model. The
designer determines what data must be stored and how the data elements
interrelate. With this information, they can begin to fit the data to the
database model.

## Creating Tables

```sql
CREATE TABLE cities (
    name VARCHAR(100),
    country VARCHAR(50),
    population INTEGER,
    area INTEGER
);
```

As you can see, the `CREATE TABLE` statement is used to create a new table. The
table is defined by its name and by the names and data types of its columns. In
this case, the table is called `cities` and it has four columns: `name`,
`country`, `population`, and `area`.

## Inserting Data

```sql
INSERT INTO cities (name, country, population, area)
VALUES ('Tokyo', 'Japan', 38505000, 8223);
```

To add multiple rows to a table, you can use a single `INSERT` statement with

```sql
INSERT INTO cities (name, country, population, area)
VALUES ('Delhi', 'India', 25840000, 573),
       ('Shanghai', 'China', 23390000, 6340),
       ('Sao Paulo', 'Brazil', 21846507, 1521),
       ('Mumbai', 'India', 18410000, 484.5),
       ('Mexico City', 'Mexico', 17400000, 1485),
       ('Beijing', 'China', 17311000, 16410),
       ('Osaka', 'Japan', 16425000, 2230),
       ('Cairo', 'Egypt', 15600000, 606),
       ('New York City', 'United States', 19354922, 468.9),
       ('Dhaka', 'Bangladesh', 15443000, 306);
```

To retrieve all rows from a table, you can use the `SELECT` statement with the
`*` wildcard character.

```sql
SELECT * FROM cities;
```

## Project 1

Write a `SELECT` statement that retrieves both rows inserted into the
`movies` table. Select both `title` and `box_office`` columns.

```sql
CREATE TABLE movies (
    title VARCHAR(100),
    box_office INTEGER
);

INSERT INTO movies (title, box_office)
VALUES ('Avatar', 27879650),
       ('Avengers: Endgame', 27978005);
```

```sql
SELECT title, box_office FROM movies;
```

## Calculated Columns

```sql
SELECT name, population, area, population / area AS population_density
FROM cities;
```

## Math Operators

- `+` Addition
- `-` Subtraction
- `*` Multiplication
- `/` Division
- `%` Modulus
- `^` Exponentiation
- `|/` Square root
- `||/` Cube root
- `!!` Factorial
- `@` Absolute value
- `&` Bitwise AND
- `|` Bitwise OR
- `#` Bitwise XOR
- `~` Bitwise NOT
- `<<` Bitwise shift left
- `>>` Bitwise shift right

## Coding Exercise 2

Take a look at the following table called phones. This
table has already been inserted into the database for you.

Write a query that will select the name of each phone and calculate the total revenue for each phone (price X units_sold)

Rename this calculated column to revenue

```sql
CREATE TABLE phones (
    name VARCHAR(100),
    price INTEGER,
    units_sold INTEGER
);

INSERT INTO phones (name, price, units_sold)
VALUES ('iPhone 12', 799, 1000000),
       ('Galaxy S21', 699, 1500000),
       ('Pixel 5', 699, 500000),
       ('OnePlus 9', 699, 300000),
       ('Xperia 1', 699, 200000);
```

```sql
SELECT name, price * units_sold AS revenue
FROM phones;
```

## String Operators and Functions

- `||` Concatenation
- `LENGTH` Length
- `UPPER` Uppercase
- `LOWER` Lowercase
- `INITCAP` Capitalize
- `TRIM` Remove leading and trailing spaces
- `LTRIM` Remove leading spaces
- `RTRIM` Remove trailing spaces
- `REPLACE` Replace a substring
- `SUBSTRING` Extract a substring
- `POSITION` Find the position of a substring
- `LEFT` Extract characters from the left
- `RIGHT` Extract characters from the right
- `REPEAT` Repeat a string
- `REVERSE` Reverse a string
- `TRANSLATE` Replace multiple characters
- `TO_CHAR` Convert a number to a string
- `TO_NUMBER` Convert a string to a number
- `TO_DATE` Convert a string to a date
- `TO_TIMESTAMP` Convert a string to a timestamp
- `TO_TIMESTAMP_TZ` Convert a string to a timestamp with time zone
- `TO_JSON` Convert a row to JSON
- `TO_JSONB` Convert a row to JSONB
- `TO_XML` Convert a row to XML
- `TO_ASCII` Convert a string to ASCII
- `TO_HEX` Convert a string to hexadecimal
- `TO_BASE64` Convert a string to base64
- `TO_BYTEA` Convert a string to bytea
- `TO_CLOB` Convert a string to CLOB

```sql
SELECT * FROM cities WHERE LENGTH(name) > 5;
```

The above query retrieves all rows from the `cities` table where the length
of column `name` is greater than 5.

## `WHERE` Clause

The `WHERE` clause is used to filter records. The `WHERE` clause is used to
extract only those records that fulfill a specified condition.

```sql
SELECT * FROM cities WHERE country = 'India';
```

The above query retrieves all rows from the `cities` table where the value of
column `country` is equal to `India`.

## Order PostgreSQL reads the `WHERE` clause
1. `FROM` and `JOIN` clauses
2. `WHERE` clause
3. `SELECT` clause

## Compound `WHERE` Clauses

```sql
SELECT * FROM cities 
         WHERE country = 'India' AND population > 20000000;
```

The above query retrieves all rows from the `cities` table where the value of
column `country` is equal to `India` and the value of column `population` is
greater than 20,000,000.

```sql
SELECT cities.name,
       cities.population
FROM
  cities
WHERE
  cities.name = 'Osaka';
```

The above query retrieves the `name` and `population` columns from the `cities`
table where the value of column `name` is equal to `Osaka`.

Let's try the `WHERE` and `IN` clauses.

```sql
SELECT cities.name,
       cities.population
FROM
  cities
WHERE
  cities.name IN ('Osaka', 'Tokyo');
```

The above query retrieves the `name` and `population` columns from the `cities`
table where the value of column `name` is either `Osaka` or `Tokyo`.

We could do the same query again and use the `NOT IN` clause.

```sql
SELECT cities.name,
       cities.population
FROM
  cities
WHERE
  cities.name NOT IN ('Osaka', 'Tokyo');
```

The above query retrieves the `name` and `population` columns from the `cities`
table where the value of column `name` is neither `Osaka` nor `Tokyo`.
