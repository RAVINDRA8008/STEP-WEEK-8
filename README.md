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

