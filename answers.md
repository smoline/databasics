## Example:
1.
 - `SQL:`
    SELECT count(\*) from items

 - `ANSWER:`
   100

---

1.
 - `SQL:`
    SELECT "count"(*) FROM users;

 - `ANSWER:`
   +---------+
   |   count |
   |---------|
   |      50 |
   +---------+


2.
 - `SQL:`
 select title from "items" order by "price" DESC limit 5;

 - `ANSWER:`
 +-----------------------+
 | title                 |
 |-----------------------|
 | Small Cotton Gloves   |
 | Small Wooden Computer |
 | Awesome Granite Pants |
 | Sleek Wooden Hat      |
 | Ergonomic Steel Car   |
 +-----------------------+

 3.
  - `SQL:`
   SELECT "title", "price" FROM "items" ORDER BY "price" limit 1;

  - `ANSWER:`
  +---------------------------+---------+
  | title                     |   price |
  |---------------------------+---------|
  | Incredible Concrete Chair |     121 |
  +---------------------------+---------+

 4.
  - `SQL:`
  SELECT users.first_name, users.last_name FROM users, addresses  WHERE users.id = addresses.user_id AND addresses.street = '6439 Zetta Hills' AND addresses.city = 'Willmouth' AND addresses.state = 'WY';

  - `ANSWER:`
  +--------------+-------------+
  | first_name   | last_name   |
  |--------------+-------------|
  | Corrine      | Little      |
  +--------------+-------------+

 5.
  - `SQL:`
  update "addresses" set "city" = 'New York', "state" = 'NY', "zip" = '10108' from users where "user_id" = (select "id" FROM "users" where "first_name" = 'Virginie' and "last_name" = 'Mitchell');

  - `ANSWER:`
  UPDATE 1
   39 | Virginie | Mitchell | daisy.crist@altenwerthmonahan.biz
   41 |  39 | 12263 Jake Crossing     | New York   | NY   | 10108

 6.
  - `SQL:`
  SELECT "sum"("price") FROM "items" where category = 'Tools';

  - `ANSWER:`
  +-------+
  |   sum |
  |-------|
  |  7383 |
  +-------+

 7.
  - `SQL:`
  SELECT "sum"("quantity") FROM "orders";

  - `ANSWER:`
  +-------+
  |   sum |
  |-------|
  |  2125 |
  +-------+

 8.
  - `SQL:`
  SELECT sum(items.price * orders.quantity) FROM orders, items WHERE orders.item_id = items.id AND items.category = 'Books';

  - `ANSWER:`
  +--------+
  |    sum |
  |--------|
  | 420566 |
  +--------+

 9.
  - `SQL:`
  INSERT INTO users(first_name, last_name, email) values('Sheri', 'Moline', 'smoline@gmail.com'); INSERT INTO addresses(user_id, street, city, state, zip) values('51', '2803 Safe Harbor Drive', 'Tampa', 'FL', '33618'); INSERT INTO orders(user_id, item_id, quantity, created_at) VALUES('51', '10', '3', '2017-03-28 09:30:20.345321');

  - `ANSWER:`
  INSERT 0 1
  INSERT 0 1
  INSERT 0 1

Adventure Mode

 1.
  - `SQL:`
  SELECT items.title, sum(orders.quantity) FROM items, orders GROUP BY items.title ORDER BY sum DESC Limit 4;

  - `ANSWER:` (There isn't just one, its a 4 way tie)
  +----------------------------+-------+
  | title                      |   sum |
  |----------------------------+-------|
  | Rustic Steel Shirt         |  4262 |
  | Ergonomic Cotton Table     |  4262 |
  | Fantastic Granite Computer |  4262 |
  | Rustic Plastic Gloves      |  4262 |
  +----------------------------+-------+

 2.
  - `SQL:`
SELECT users.first_name, users.last_name, sum(orders.quantity * items.price) FROM users, orders, items WHERE users.id = orders.user_id AND orders.item_id = items.id GROUP BY users.last_name, users.first_name ORDER BY sum DESC limit 1;

  - `ANSWER:`
  +--------------+-------------+--------+
  | first_name   | last_name   |    sum |
  |--------------+-------------+--------|
  | Hassan       | Runte       | 639386 |
  +--------------+-------------+--------+

 3.
  - `SQL:`
SELECT items.category, sum(orders.quantity * items.price) FROM items, orders GROUP BY items.category ORDER BY sum DESC limit 3;

  - `ANSWER:`
  +------------+----------+
  | category   |      sum |
  |------------+----------|
  | Books      | 48377962 |
  | Sports     | 45313584 |
  | Toys       | 40248197 |
  +------------+----------+
