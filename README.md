## Databasics

### To learn how to create SQL(postgresql) statements

Before closing the homework assignment issue:

- Update answers.md:
  - For each question include the SQL statement(s) you wrote to generate the answer.
  - For each question include the *answer* (the sqlite output), if any, to the question asked.

### Setup

```
createdb databasics
psql databasics < create.sql
```

### Running the CLI

```
pgcli databasics
```

### To restore your database if you need to reset it:

```
dropdb databasics
createdb databasics
psql databasics < create.sql
```

### Explorer Mode

1. How many users are there?
1. What are the titles of the 5 most expensive items?
1. What's the cheapest item in the `Books` category?
1. Who lives at 6439 Zetta Hills, Willmouth, WY?
1. Correct Virginie Mitchell's address to "New York, NY, 10108".
1. How much would it cost to buy one of each item in the `Tools` category?
1. How many total items did we sell?
1. How much was spent on `Books`?
1. Simulate buying an item by inserting a User for yourself and an Order for yourself.

### Adventure Mode

1. What item was ordered the most?
1. What user spent the most?
1. What were the top 3 highest grossing categories?
