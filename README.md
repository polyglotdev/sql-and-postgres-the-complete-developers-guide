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
