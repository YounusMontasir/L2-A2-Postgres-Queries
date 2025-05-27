# PostgreSQL Basics

## 1. Explain the Primary Key and Foreign Key concepts in PostgreSQL

**Primary Key**:  
A primary key is unique for each record in a table. It helps identify individual rows.  
*Example*: In a `student` table with columns like `name`, `id`, `address`, and `result`, the `id` must be unique for each student. So, `id` is a good choice for a primary key because it can uniquely identify each student.

**Foreign Key**:  
A foreign key is a field (or collection of fields) in one table that uniquely identifies a row of another table.  
*Example*: In a `course` table with fields `course_id`, `course_duration`, `course_name`, and `student_id`, `course_id` is the primary key. The `student_id` refers to the `id` in the `student` table, making it a foreign key.

---

## 2. What is the difference between the `VARCHAR` and `CHAR` data types?

- **`VARCHAR(n)`**: A variable-length string with a maximum length of `n`.  
  *Example*: If `VARCHAR(15)` is used and we insert `'next level'`, it will use only 10 characters.

- **`CHAR(n)`**: A fixed-length string that always uses `n` characters.  
  *Example*: If `CHAR(15)` is used and we insert `'next level'`, it will still occupy 15 characters, with trailing spaces padded.

---

## 3. What are the `LIMIT` and `OFFSET` clauses used for?

- **`LIMIT`**: Specifies the maximum number of rows to return.  
  *Example*:
  ```sql
  SELECT * FROM students LIMIT 5;
  ```
  → This returns 5 rows.

- **`OFFSET`**: Skips a specified number of rows before beginning to return rows.  
  *Example*:
  ```sql
  SELECT * FROM students OFFSET 5;
  ```
  → This skips the first 5 rows.

---

## 4. What is the significance of the `JOIN` operation, and how does it work in PostgreSQL?

`JOIN` is used to combine rows from two or more tables based on a related column between them.

Types of joins:
- `INNER JOIN`
- `LEFT JOIN`
- `RIGHT JOIN`
- `FULL JOIN`
- `CROSS JOIN`
- `OUTER JOIN`

*Example*: Joining student and course data using `student_id` to get combined information.

---

## 5. How can you calculate aggregate functions like `COUNT()`, `SUM()`, and `AVG()` in PostgreSQL?

Assuming a `students` table with a `marks` column:

- **Count**:
  ```sql
  SELECT COUNT(*) FROM students;
  ```

- **Sum**:
  ```sql
  SELECT SUM(marks) FROM students;
  ```

- **Average**:
  ```sql
  SELECT AVG(marks) FROM students;
  ```
