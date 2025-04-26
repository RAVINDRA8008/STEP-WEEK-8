# STEP-WEEK-8
## Basic SQL Structure (`SELECT`, `FROM`, `WHERE`, etc.)

### Topic 1: Basic SELECT with WHERE

---

#### Lab 1.1 – Task
**Retrieve the details of all users whose name starts with the letter 'S'.**



#### Question
Write an SQL query to get all users whose names start with 'S'.


#### Answer
```sql
SELECT *
FROM user
WHERE name LIKE 'S%';
```


#### Explanation

- **`SELECT *`**  
  Selects all columns (fields) from the table.

- **`FROM user`**  
  Specifies that the data is being selected from the `user` table.

- **`WHERE name LIKE 'S%'`**  
  - `WHERE` is used to filter the rows based on a condition.
  - `name LIKE 'S%'` means the name should start with the letter **S**.
  - `%` is a wildcard character that matches any sequence of characters after **S**.

---
---

#### Lab 1.2 – Task
**Retrieve all movies where the genre is 'Comedy'.**

#### Question
Write an SQL query to get all movies with the genre 'Comedy'.

#### Answer
```sql
SELECT *
FROM movie
WHERE genre = 'Comedy';
```

#### Explanation

- **`SELECT *`**  
  Selects all columns (fields) from the table.

- **`FROM movie`**  
  Specifies that the data is being selected from the `movie` table.

- **`WHERE genre = 'Comedy'`**  
  - `WHERE` filters the rows based on a condition.
  - `genre = 'Comedy'` means only the rows where the genre is exactly 'Comedy' will be retrieved.
  - The condition must match exactly, including letter casing (depending on the database settings).

---

---

#### Lab 1.3 – Task
**Display the `booking_id`, `user_id`, and `total_amount` for bookings made by user with ID 102.**

#### Question
Write an SQL query to get the `booking_id`, `user_id`, and `total_amount` for bookings made by user ID 102.

#### Answer
```sql
SELECT booking_id, user_id, total_cost AS total_amount
FROM booking
WHERE user_id = 102;
```

#### Explanation

- **`SELECT booking_id, user_id, total_cost AS total_amount`**  
  Selects the columns `booking_id` and `user_id` from the `booking` table.  
  It also selects `total_cost` and renames it as `total_amount` using the `AS` keyword.

- **`FROM booking`**  
  Specifies that the data is being selected from the `booking` table.

- **`WHERE user_id = 102`**  
  - Filters the results to include only rows where the `user_id` is exactly 102.
  - Only bookings made by user 102 will be shown.

---
---

### Topic 2: SELECT with WHERE using Operators (=, >, <, !=)

---


#### Lab 2.1 – Task
**List all movie names where the rating is greater than 4.0.**

#### Question
Write an SQL query to retrieve all movie titles with a rating higher than 4.0.

#### Answer
```sql
SELECT title
FROM movie
WHERE rating > 4.0;
```

#### Explanation

- **`SELECT title`**  
  Retrieves only the `title` column from the result set (i.e., the names of the movies).

- **`FROM movie`**  
  Specifies that the data should come from the `movie` table.

- **`WHERE rating > 4.0`**  
  - Filters the rows to only include movies with a `rating` greater than 4.0.
  - The `>` operator checks for values strictly greater than 4.0.

---
---

#### Lab 2.2 – Task
**List all bookings where the total amount is greater than ₹400.**

#### Question
Write an SQL query to get the `booking_id`, `user_id`, and `total_cost` for bookings where the total amount exceeds ₹400.

#### Answer
```sql
SELECT booking_id, user_id, total_cost
FROM booking
WHERE total_cost > 400;
```

#### Explanation

- **`SELECT booking_id, user_id, total_cost`**  
  Retrieves the `booking_id`, `user_id`, and `total_cost` columns from the `booking` table.

- **`FROM booking`**  
  Indicates that the data is being fetched from the `booking` table.

- **`WHERE total_cost > 400`**  
  - Filters the records to include only those where the `total_cost` is greater than 400.
  - The `>` operator checks for values strictly greater than 400.

---
