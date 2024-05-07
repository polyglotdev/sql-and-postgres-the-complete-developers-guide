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
