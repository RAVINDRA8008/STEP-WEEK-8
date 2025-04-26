# STEP-WEEK-8
# Basic SQL Structure (SELECT, FROM, WHERE, etc.)

## Topic 1: Basic SELECT with WHERE

---

### Lab 1.1 – Task
**Retrieve the details of all users whose name starts with the letter 'S'.**

---

### Question
Write an SQL query to get all users whose names start with 'S'.

---

### Answer
```sql
SELECT *
FROM user
WHERE name LIKE 'S%';
