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
---

### Topic 3: SELECT with WHERE using AND/OR
---

#### Lab 3.1 – Task
**Show details where movie ID is 3 and the show datetime is after '2025-04-20'.**

#### Question
Write an SQL query to retrieve all details from the `show` table where the `movie_id` is 3 and the `show_datetime` is after '2025-04-20'.

#### Answer
```sql
SELECT *
FROM show
WHERE movie_id = 3 AND show_datetime > '2025-04-20';
```

#### Explanation

- **`SELECT *`**  
  Selects all columns from the `show` table.

- **`FROM show`**  
  Specifies that the data is being fetched from the `show` table.

- **`WHERE movie_id = 3 AND show_datetime > '2025-04-20'`**  
  - The condition checks two things:  
    - `movie_id = 3` ensures that only rows with `movie_id` equal to 3 are included.
    - `show_datetime > '2025-04-20'` ensures that only shows after April 20th, 2025, are included.
  - The `AND` operator is used to combine these two conditions, meaning both conditions must be true for a row to be included.

---
---

#### Lab 3.2 – Task
**List all bookings where the total cost is more than ₹500 OR the booking was made after '2025-04-01'.**

#### Question
Write an SQL query to retrieve all bookings where the `total_cost` is more than ₹500 or the `booking_datetime` is after '2025-04-01'.

#### Answer
```sql
SELECT *
FROM booking
WHERE total_cost > 500 OR booking_datetime > '2025-04-01';
```

#### Explanation

- **`SELECT *`**  
  Selects all columns from the `booking` table.

- **`FROM booking`**  
  Specifies that the data is being fetched from the `booking` table.

- **`WHERE total_cost > 500 OR booking_datetime > '2025-04-01'`**  
  - This condition includes rows where either:
    - The `total_cost` is greater than ₹500, or
    - The `booking_datetime` is later than April 1st, 2025.
  - The `OR` operator is used here, meaning if either of the conditions is true, the row will be included.

---
---

### Topic 4: SELECT with WHERE and NOT
---
#### Lab 4.1 – Task
**Show all food items which are not combos.**

#### Question
Write an SQL query to retrieve all food items that are not combos.

#### Answer
```sql
SELECT *
FROM fooditem
WHERE NOT is_combo = 'TRUE';
```

#### Explanation

- **`SELECT *`**  
  Selects all columns from the `fooditem` table.

- **`FROM fooditem`**  
  Specifies that the data is being fetched from the `fooditem` table.

- **`WHERE NOT is_combo = 'TRUE'`**  
  - The `NOT` operator negates the condition. It selects rows where the value of `is_combo` is **not** equal to `'TRUE'`.
  - This effectively retrieves all food items that are not considered combos.

---

#### Lab 4.2 – Task
**Get all movie details that are not in status 'Inactive'.**

#### Question
Write an SQL query to retrieve all movie details where the status is not 'Inactive'.

#### Answer
```sql
SELECT *
FROM movie
WHERE status != 'Inactive';
```

#### Explanation

- **`SELECT *`**  
  Selects all columns from the `movie` table.

- **`FROM movie`**  
  Specifies that the data is being fetched from the `movie` table.

- **`WHERE status != 'Inactive'`**  
  - The `!=` operator checks for inequality.
  - This condition retrieves all rows where the `status` is not equal to `'Inactive'`.

---
---

### Topic 5: SELECT with WHERE and BETWEEN
---
#### Lab 5.1 – Task
**List all food sizes where the rate is between 150 and 300.**

#### Question
Write an SQL query to retrieve all food item sizes where the `rate` falls between 150 and 300.

#### Answer
```sql
SELECT *
FROM FoodItemSize
WHERE rate BETWEEN 150 AND 300;
```

#### Explanation

- **`SELECT *`**  
  Selects all columns from the `FoodItemSize` table.

- **`FROM FoodItemSize`**  
  Specifies that the data is being fetched from the `FoodItemSize` table.

- **`WHERE rate BETWEEN 150 AND 300`**  
  - The `BETWEEN` operator checks if the `rate` is within the specified range (inclusive of 150 and 300).
  - This retrieves all records where the `rate` is greater than or equal to 150 and less than or equal to 300.

---
---

#### Lab 5.2 – Task
**Get all ticket bookings between '2025-04-01' and '2025-04-10'.**

#### Question
Write an SQL query to retrieve all bookings made between '2025-04-01' and '2025-04-10'.

#### Answer
```sql
SELECT *
FROM booking
WHERE booking_datetime BETWEEN '2025-04-01' AND '2025-04-10 23:59:59';
```

#### Explanation

- **`SELECT *`**  
  Selects all columns from the `booking` table.

- **`FROM booking`**  
  Specifies that the data is being fetched from the `booking` table.

- **`WHERE booking_datetime BETWEEN '2025-04-01' AND '2025-04-10 23:59:59'`**  
  - The `BETWEEN` operator checks if `booking_datetime` falls within the specified range.
  - It includes all bookings from the start of April 1st, 2025, up to the very end of April 10th, 2025 (`23:59:59`).

---
---

### Topic 6: SELECT with WHERE and IN

#### Lab 6.1 – Task
**Display food items whose names are either 'Vintage Cola', 'Sweet & Salty Popcorn', or 'Fiesta Nachos'.**

#### Question
Write an SQL query to retrieve food items where the name matches any of the specified items.

#### Answer
```sql
SELECT *
FROM fooditem
WHERE name IN ('Vintage Cola', 'Sweet & Salty Popcorn', 'Fiesta Nachos');
```

#### Explanation

- **`SELECT *`**  
  Selects all columns from the `fooditem` table.

- **`FROM fooditem`**  
  Specifies that the data is being fetched from the `fooditem` table.

- **`WHERE name IN ('Vintage Cola', 'Sweet & Salty Popcorn', 'Fiesta Nachos')`**  
  - The `IN` operator checks if the `name` value matches any value in the provided list.
  - Only food items with names exactly matching one of the listed names will be retrieved.

---
---

#### Lab 6.2 – Task
**List all bookings made by users with user IDs 101, 103, or 105.**

#### Question
Write an SQL query to retrieve all bookings made by users with IDs 101, 103, or 105.

#### Answer
```sql
SELECT *
FROM booking
WHERE user_id IN (101, 103, 105);
```

#### Explanation

- **`SELECT *`**  
  Selects all columns from the `booking` table.

- **`FROM booking`**  
  Specifies that the data is being fetched from the `booking` table.

- **`WHERE user_id IN (101, 103, 105)`**  
  - The `IN` operator checks if the `user_id` is one of the specified values.
  - Only bookings made by users with IDs 101, 103, or 105 will be retrieved.

---
---

### Topic 8: SELECT with ORDER BY (ASC/DESC)

#### Lab 8.1 – Task
**List all movies ordered by their rating in descending order.**

#### Question
Write an SQL query to retrieve all movies sorted by their rating from highest to lowest.

#### Answer
```sql
SELECT *
FROM movie
ORDER BY rating DESC;
```

#### Explanation

- **`SELECT *`**  
  Retrieves all columns from the `movie` table.

- **`FROM movie`**  
  Specifies that the data is being fetched from the `movie` table.

- **`ORDER BY rating DESC`**  
  - Orders the result set based on the `rating` column.
  - `DESC` (Descending) means the highest ratings will appear first.

---
---

#### Lab 8.2 – Task
**List all shows ordered by `show_datetime` in ascending order.**

#### Question
Write an SQL query to retrieve all shows sorted by `show_datetime` from earliest to latest.

#### Answer
```sql
SELECT *
FROM show
ORDER BY show_datetime ASC;
```

#### Explanation

- **`SELECT *`**  
  Retrieves all columns from the `show` table.

- **`FROM show`**  
  Specifies that the data is being fetched from the `show` table.

- **`ORDER BY show_datetime ASC`**  
  - Orders the result set based on the `show_datetime` column.
  - `ASC` (Ascending) means earlier dates and times will appear first.

---
---

### Topic 9: SELECT with ALIAS (column and table aliases)

#### Lab 9.1 – Task
**Get the names and ratings of movies, but label the rating as 'Movie Rating'.**

#### Question
Write an SQL query to retrieve movie titles and ratings, with the rating column renamed as "Movie Rating".

#### Answer
```sql
SELECT title, rating AS "Movie Rating"
FROM Movie;
```

#### Explanation

- **`SELECT title, rating AS "Movie Rating"`**  
  - Retrieves the `title` column as it is.
  - Renames the `rating` column as "Movie Rating" using the `AS` keyword for better readability in the output.

- **`FROM Movie`**  
  Specifies that the data is being fetched from the `Movie` table.

---
---
#### Lab 9.2 – Task
**Show screen names and their types, but alias `class_type` as "Screen Class".**

#### Question
Write an SQL query to retrieve screen names and types, with `class_type` renamed as "Screen Class".

#### Answer
```sql
SELECT name, class_type AS "Screen Class"
FROM Screen;
```

#### Explanation

- **`SELECT name, class_type AS "Screen Class"`**  
  - Retrieves the `name` column as it is.
  - Renames the `class_type` column as "Screen Class" using the `AS` keyword.

- **`FROM Screen`**  
  Specifies that the data is being fetched from the `Screen` table.

---
