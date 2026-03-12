

# 🗺️ ROADMAP: SQL — Complete Mastery Guide

> From `SELECT *` to Query Optimization — Everything You Need

---

## 📊 Roadmap Overview

```
Total Estimated Time: 8–10 Weeks (2 hrs/day)
Difficulty Curve:     ████████░░ (Starts easy, gets deep)
Relevance:            Exams ⭐⭐⭐⭐⭐ | Placements ⭐⭐⭐⭐⭐ | GATE ⭐⭐⭐⭐ | Jobs ⭐⭐⭐⭐⭐
```

```
🔴 = Critical (MUST know — asked everywhere)
🟡 = Important (frequently tested)
🟢 = Good to Know (gives you an edge)
```

---

## 🧱 PHASE 1: FOUNDATIONS (Week 1)
### *"Understand what you're working with before writing queries"*

```
⏱️ Estimated: 6–8 hours
Prerequisites: None (absolute beginner friendly)
```

| # | Topic | Priority | Hours | Key Concepts |
|---|-------|----------|-------|-------------|
| 1 | What are Databases? | 🔴 | 0.5 | Why databases exist, File vs DB |
| 2 | Relational Databases (RDBMS) | 🔴 | 1 | Tables, Rows, Columns, Schema |
| 3 | RDBMS Benefits & Limitations | 🟡 | 0.5 | ACID, Redundancy, Scalability issues |
| 4 | SQL vs NoSQL | 🟡 | 1 | When to use which, key differences |
| 5 | Install & Setup | 🔴 | 1 | MySQL/PostgreSQL + a GUI tool |
| 6 | SQL Data Types | 🔴 | 1 | INT, VARCHAR, DATE, FLOAT, BOOLEAN, TEXT |
| 7 | SQL Keywords & Syntax Rules | 🔴 | 1 | Case insensitivity, semicolons, comments |
| 8 | Operators | 🔴 | 1 | Arithmetic, Comparison, Logical (AND/OR/NOT), BETWEEN, IN, LIKE |

### 🧒 ELI5 — What is a Relational Database?

> Think of it like an **Excel spreadsheet on steroids**.
> Each sheet = a **Table**
> Each row = one **Record** (e.g., one student)
> Each column = an **Attribute** (e.g., name, roll_no, CGPA)
> The "relational" part? Tables can **link to each other** — like your Aadhaar connecting to your bank, your PAN, your phone number.

### 💻 Setup Recommendation

```
FOR BEGINNERS:
├── Option 1: MySQL + MySQL Workbench (most used in Indian colleges)
├── Option 2: PostgreSQL + pgAdmin (industry preferred)
├── Option 3: SQLite + DB Browser (zero setup, lightweight)
└── Option 4: Online — db-fiddle.com or sqliteonline.com (no install needed)

🎯 RECOMMENDED: Start with MySQL (college exams) → Move to PostgreSQL (jobs/interviews)
```

### 📝 Practice Task — Phase 1
```sql
-- Create your first database and table
CREATE DATABASE college;
USE college;

CREATE TABLE students (
    roll_no     INT PRIMARY KEY,
    name        VARCHAR(50) NOT NULL,
    branch      VARCHAR(30),
    cgpa        DECIMAL(3,2),
    admission   DATE
);

-- Insert some data
INSERT INTO students VALUES (101, 'Rahul Sharma', 'CSE', 8.5, '2022-08-01');
INSERT INTO students VALUES (102, 'Priya Patel', 'CSE', 9.1, '2022-08-01');
INSERT INTO students VALUES (103, 'Amit Kumar', 'ECE', 7.8, '2022-08-02');
```

---

## 🧱 PHASE 2: CORE SQL — DDL & DML (Week 2)
### *"The bread and butter — you'll use this EVERY single day"*

```
⏱️ Estimated: 8–10 hours
Prerequisites: Phase 1
```

### 📦 Data Definition Language (DDL) — *Structure*

| # | Topic | Priority | What It Does |
|---|-------|----------|-------------|
| 1 | `CREATE TABLE` | 🔴 | Creates a new table |
| 2 | `ALTER TABLE` | 🔴 | Modify structure (add/drop/rename columns) |
| 3 | `DROP TABLE` | 🔴 | Permanently delete table |
| 4 | `TRUNCATE TABLE` | 🟡 | Delete all rows but keep structure |

```sql
-- DDL Examples

-- Create
CREATE TABLE employees (
    emp_id    INT PRIMARY KEY AUTO_INCREMENT,
    name      VARCHAR(100) NOT NULL,
    dept      VARCHAR(50),
    salary    DECIMAL(10,2) DEFAULT 30000.00,
    join_date DATE
);

-- Alter — Add column
ALTER TABLE employees ADD email VARCHAR(100);

-- Alter — Modify column
ALTER TABLE employees MODIFY salary DECIMAL(12,2);

-- Alter — Drop column
ALTER TABLE employees DROP COLUMN email;

-- Truncate vs Drop
TRUNCATE TABLE employees;  -- Deletes data, keeps table structure
DROP TABLE employees;      -- Deletes EVERYTHING (table gone!)
```

### ⚡ Key Difference (Exam Favourite!)

```
┌──────────────┬────────────────┬────────────────┬────────────────┐
│   Feature    │    DELETE      │   TRUNCATE     │     DROP       │
├──────────────┼────────────────┼────────────────┼────────────────┤
│ Type         │ DML            │ DDL            │ DDL            │
│ WHERE clause │ ✅ Yes         │ ❌ No          │ ❌ No          │
│ Rollback     │ ✅ Possible    │ ❌ Not possible│ ❌ Not possible│
│ Speed        │ Slow (row-by-row)│ Fast (bulk)  │ Fastest        │
│ Table exists?│ ✅ Yes         │ ✅ Yes         │ ❌ No          │
│ Triggers     │ ✅ Fired       │ ❌ Not fired   │ ❌ Not fired   │
│ Auto-increment│ Continues     │ Resets         │ N/A            │
└──────────────┴────────────────┴────────────────┴────────────────┘
```

### 📝 Data Manipulation Language (DML) — *The Data*

| # | Statement | Priority | Purpose |
|---|-----------|----------|---------|
| 1 | `SELECT` | 🔴 | Read/retrieve data |
| 2 | `INSERT` | 🔴 | Add new records |
| 3 | `UPDATE` | 🔴 | Modify existing records |
| 4 | `DELETE` | 🔴 | Remove specific records |

```sql
-- INSERT — Multiple formats
INSERT INTO employees (name, dept, salary, join_date)
VALUES ('Sneha Gupta', 'Engineering', 75000, '2023-06-15');

-- INSERT multiple rows at once
INSERT INTO employees (name, dept, salary, join_date) VALUES
  ('Rohit Singh', 'Marketing', 55000, '2023-07-01'),
  ('Ananya Das', 'Engineering', 82000, '2023-05-10'),
  ('Karan Mehta', 'HR', 48000, '2023-08-20');

-- UPDATE (⚠️ ALWAYS use WHERE — or you'll update EVERY row!)
UPDATE employees 
SET salary = 80000 
WHERE emp_id = 1;

-- DELETE (⚠️ ALWAYS use WHERE — or you'll delete EVERYTHING!)
DELETE FROM employees 
WHERE dept = 'Marketing' AND salary < 40000;
```

> ⚠️ **Golden Rule**: Never run `UPDATE` or `DELETE` without `WHERE` unless you're absolutely sure. This is how production databases get destroyed in real companies.

---

## 🧱 PHASE 3: SELECT Mastery (Week 2–3)
### *"80% of SQL in real life is just reading data intelligently"*

```
⏱️ Estimated: 10–12 hours
Prerequisites: Phase 2
This is the MOST important phase. Master this thoroughly.
```

### 📐 SELECT Query Anatomy

```sql
SELECT column1, column2, ...     -- 5. What columns to show
FROM table_name                   -- 1. Which table
WHERE condition                   -- 2. Filter rows
GROUP BY column                   -- 3. Group rows
HAVING condition                  -- 4. Filter groups
ORDER BY column ASC/DESC          -- 6. Sort results
LIMIT n;                          -- 7. Limit output rows

-- ⚡ EXECUTION ORDER (not the writing order!):
-- FROM → WHERE → GROUP BY → HAVING → SELECT → ORDER BY → LIMIT
-- 🎯 This is asked in interviews! Know this.
```

### Complete SELECT Toolkit

| # | Clause/Feature | Priority | Example |
|---|---------------|----------|---------|
| 1 | `SELECT *` / specific columns | 🔴 | `SELECT name, salary FROM employees` |
| 2 | `WHERE` with conditions | 🔴 | `WHERE salary > 50000 AND dept = 'CSE'` |
| 3 | `ORDER BY` (ASC/DESC) | 🔴 | `ORDER BY salary DESC` |
| 4 | `LIMIT` / `TOP` | 🔴 | `LIMIT 10` |
| 5 | `DISTINCT` | 🔴 | `SELECT DISTINCT dept FROM employees` |
| 6 | `LIKE` pattern matching | 🔴 | `WHERE name LIKE 'A%'` (starts with A) |
| 7 | `IN` operator | 🔴 | `WHERE dept IN ('CSE', 'ECE', 'IT')` |
| 8 | `BETWEEN` | 🟡 | `WHERE salary BETWEEN 40000 AND 80000` |
| 9 | `IS NULL` / `IS NOT NULL` | 🔴 | `WHERE email IS NULL` |
| 10 | `ALIASES` (AS) | 🟡 | `SELECT name AS student_name` |

```sql
-- Real-world style queries for practice

-- 1. Find top 5 highest-paid employees in Engineering
SELECT name, salary 
FROM employees 
WHERE dept = 'Engineering' 
ORDER BY salary DESC 
LIMIT 5;

-- 2. Find employees whose name starts with 'S' and salary > 60k
SELECT * FROM employees 
WHERE name LIKE 'S%' AND salary > 60000;

-- 3. Find departments that have employees (no NULL dept)
SELECT DISTINCT dept 
FROM employees 
WHERE dept IS NOT NULL;

-- 4. LIKE patterns (very important!)
-- 'A%'     → starts with A
-- '%a'     → ends with a
-- '%kumar%'→ contains 'kumar' anywhere
-- '_a%'    → second character is 'a'
-- '___'    → exactly 3 characters
```

---

## 🧱 PHASE 4: AGGREGATE QUERIES (Week 3)
### *"Summarize data — counts, averages, totals"*

```
⏱️ Estimated: 6–8 hours
Priority: 🔴 Critical — asked in EVERY exam and interview
```

### Aggregate Functions

| Function | What It Does | Example |
|----------|-------------|---------|
| `COUNT()` | Count rows | `COUNT(*)` or `COUNT(column)` |
| `SUM()` | Total of values | `SUM(salary)` |
| `AVG()` | Average | `AVG(cgpa)` |
| `MIN()` | Minimum value | `MIN(salary)` |
| `MAX()` | Maximum value | `MAX(salary)` |

### GROUP BY + HAVING (The Power Combo)

```sql
-- Average salary per department
SELECT dept, AVG(salary) AS avg_salary
FROM employees
GROUP BY dept;

-- Departments with more than 5 employees
SELECT dept, COUNT(*) AS emp_count
FROM employees
GROUP BY dept
HAVING COUNT(*) > 5;

-- Department with highest total salary bill
SELECT dept, SUM(salary) AS total_salary
FROM employees
GROUP BY dept
ORDER BY total_salary DESC
LIMIT 1;
```

### 🧒 ELI5 — GROUP BY vs HAVING vs WHERE

```
Imagine you're organizing a college fest:

WHERE  = "Only invite CSE and ECE students"
         (Filters INDIVIDUAL students BEFORE grouping)

GROUP BY = "Now group them by their year (1st, 2nd, 3rd, 4th)"
           (Creates groups)

HAVING = "Only keep groups that have more than 20 students"
         (Filters GROUPS after grouping)

┌─────────┬──────────────────────────────────────────────┐
│         │ WHERE filters rows BEFORE grouping           │
│ KEY     │ HAVING filters groups AFTER grouping          │
│ DIFF    │ WHERE can't use aggregate functions           │
│         │ HAVING can use aggregate functions            │
└─────────┴──────────────────────────────────────────────┘
```

```sql
-- ❌ WRONG: Can't use aggregate in WHERE
SELECT dept, AVG(salary) 
FROM employees 
WHERE AVG(salary) > 50000   -- ERROR!
GROUP BY dept;

-- ✅ CORRECT: Use HAVING for aggregate conditions
SELECT dept, AVG(salary) 
FROM employees 
GROUP BY dept 
HAVING AVG(salary) > 50000;  -- Works!
```

---

## 🧱 PHASE 5: DATA CONSTRAINTS (Week 3–4)
### *"Rules that keep your data clean and consistent"*

```
⏱️ Estimated: 4–5 hours
Priority: 🔴 Critical for exams + database design interviews
```

| Constraint | Purpose | Example |
|-----------|---------|---------|
| `PRIMARY KEY` | 🔴 Uniquely identifies each row | `roll_no INT PRIMARY KEY` |
| `FOREIGN KEY` | 🔴 Links two tables | `REFERENCES departments(dept_id)` |
| `UNIQUE` | 🟡 No duplicate values (but allows NULL) | `email VARCHAR(100) UNIQUE` |
| `NOT NULL` | 🔴 Column can't be empty | `name VARCHAR(50) NOT NULL` |
| `CHECK` | 🟡 Custom validation rule | `CHECK (age >= 18)` |
| `DEFAULT` | 🟢 Auto-fill if not provided | `status VARCHAR(10) DEFAULT 'active'` |

```sql
CREATE TABLE orders (
    order_id    INT PRIMARY KEY AUTO_INCREMENT,
    customer_id INT NOT NULL,
    product     VARCHAR(100) NOT NULL,
    quantity    INT CHECK (quantity > 0),
    price       DECIMAL(10,2) NOT NULL,
    status      VARCHAR(20) DEFAULT 'pending',
    order_date  DATE NOT NULL,
    
    -- Foreign Key linking to customers table
    FOREIGN KEY (customer_id) REFERENCES customers(id)
        ON DELETE CASCADE      -- if customer deleted, delete their orders
        ON UPDATE CASCADE      -- if customer id changes, update here too
);
```

### 🔑 PRIMARY KEY vs UNIQUE (Exam Question!)

```
┌──────────────────┬────────────────┬────────────────┐
│    Feature       │ PRIMARY KEY    │ UNIQUE         │
├──────────────────┼────────────────┼────────────────┤
│ NULL allowed?    │ ❌ Never       │ ✅ One NULL     │
│ Per table        │ Only ONE       │ Multiple       │
│ Creates index    │ Clustered      │ Non-clustered  │
│ Purpose          │ Row identity   │ Prevent dupes  │
└──────────────────┴────────────────┴────────────────┘
```

---

## 🧱 PHASE 6: JOINs (Week 4–5)
### *"The MOST important topic in SQL — period."*

```
⏱️ Estimated: 10–12 hours
Priority: 🔴🔴🔴 — Asked in EVERY interview, EVERY exam, EVERY GATE paper
Prerequisites: Phase 5 (understand FK relationships)
```

### Setup — Two Tables to Practice

```sql
-- Table 1: Students
CREATE TABLE students (
    id      INT PRIMARY KEY,
    name    VARCHAR(50),
    dept_id INT
);

INSERT INTO students VALUES
(1, 'Rahul', 101),
(2, 'Priya', 102),
(3, 'Amit', 101),
(4, 'Sneha', NULL),    -- No department assigned
(5, 'Karan', 103);

-- Table 2: Departments
CREATE TABLE departments (
    dept_id   INT PRIMARY KEY,
    dept_name VARCHAR(50)
);

INSERT INTO departments VALUES
(101, 'CSE'),
(102, 'ECE'),
(104, 'Mechanical');   -- Note: 104 exists but no student has it
                        -- Note: 103 has a student but no dept entry
```

### All JOIN Types — Visual + Code

```
Students Table:          Departments Table:
┌────┬───────┬─────┐    ┌─────┬────────────┐
│ id │ name  │dept_│    │dept_│ dept_name  │
│    │       │ id  │    │ id  │            │
├────┼───────┼─────┤    ├─────┼────────────┤
│ 1  │ Rahul │ 101 │    │ 101 │ CSE        │
│ 2  │ Priya │ 102 │    │ 102 │ ECE        │
│ 3  │ Amit  │ 101 │    │ 104 │ Mechanical │
│ 4  │ Sneha │NULL │    └─────┴────────────┘
│ 5  │ Karan │ 103 │
└────┴───────┴─────┘
```

---

### 1️⃣ INNER JOIN 🔴

> **Only matching rows from BOTH tables**

```
    ┌─────────┐     ┌─────────┐
    │ Students│     │  Depts  │
    │    ┌────┼─────┼────┐    │
    │    │████│█████│████│    │
    │    │████│INNER│████│    │
    │    │████│█████│████│    │
    │    └────┼─────┼────┘    │
    └─────────┘     └─────────┘
         Only the overlap
```

```sql
SELECT s.name, d.dept_name
FROM students s
INNER JOIN departments d ON s.dept_id = d.dept_id;

-- Result:
-- ┌───────┬───────────┐
-- │ name  │ dept_name │
-- ├───────┼───────────┤
-- │ Rahul │ CSE       │
-- │ Priya │ ECE       │
-- │ Amit  │ CSE       │
-- └───────┴───────────┘
-- ❌ Sneha (NULL dept_id — no match)
-- ❌ Karan (dept_id 103 — not in departments table)
-- ❌ Mechanical (dept_id 104 — no student has it)
```

---

### 2️⃣ LEFT JOIN (LEFT OUTER JOIN) 🔴

> **ALL rows from LEFT table + matching from right (NULL if no match)**

```
    ┌─────────┐     ┌─────────┐
    │█████████│     │         │
    │█████████│     │         │
    │████┌────┼─────┼────┐    │
    │████│████│█████│████│    │
    │████└────┼─────┼────┘    │
    │█████████│     │         │
    └─────────┘     └─────────┘
    ALL of left + matching right
```

```sql
SELECT s.name, d.dept_name
FROM students s
LEFT JOIN departments d ON s.dept_id = d.dept_id;

-- Result:
-- ┌───────┬────────────┐
-- │ name  │ dept_name  │
-- ├───────┼────────────┤
-- │ Rahul │ CSE        │
-- │ Priya │ ECE        │
-- │ Amit  │ CSE        │
-- │ Sneha │ NULL       │  ← kept, but no match
-- │ Karan │ NULL       │  ← kept, but no match
-- └───────┴────────────┘
```

---

### 3️⃣ RIGHT JOIN (RIGHT OUTER JOIN) 🟡

> **ALL rows from RIGHT table + matching from left**

```sql
SELECT s.name, d.dept_name
FROM students s
RIGHT JOIN departments d ON s.dept_id = d.dept_id;

-- Result:
-- ┌───────┬────────────┐
-- │ name  │ dept_name  │
-- ├───────┼────────────┤
-- │ Rahul │ CSE        │
-- │ Amit  │ CSE        │
-- │ Priya │ ECE        │
-- │ NULL  │ Mechanical │  ← No student, but dept kept
-- └───────┴────────────┘
```

---

### 4️⃣ FULL OUTER JOIN 🟡

> **ALL rows from BOTH tables — NULL where no match**

```sql
-- MySQL doesn't support FULL OUTER JOIN directly. Use UNION:
SELECT s.name, d.dept_name
FROM students s
LEFT JOIN departments d ON s.dept_id = d.dept_id

UNION

SELECT s.name, d.dept_name
FROM students s
RIGHT JOIN departments d ON s.dept_id = d.dept_id;

-- Result:
-- ┌───────┬────────────┐
-- │ name  │ dept_name  │
-- ├───────┼────────────┤
-- │ Rahul │ CSE        │
-- │ Priya │ ECE        │
-- │ Amit  │ CSE        │
-- │ Sneha │ NULL       │
-- │ Karan │ NULL       │
-- │ NULL  │ Mechanical │
-- └───────┴────────────┘
```

---

### 5️⃣ SELF JOIN 🟡

> **A table joins with ITSELF** (used for hierarchies, comparisons)

```sql
-- Find employees who earn more than their manager
SELECT e.name AS employee, m.name AS manager, e.salary
FROM employees e
JOIN employees m ON e.manager_id = m.emp_id
WHERE e.salary > m.salary;
```

---

### 6️⃣ CROSS JOIN 🟢

> **Every row × Every row (Cartesian Product)**

```sql
SELECT s.name, d.dept_name
FROM students s
CROSS JOIN departments d;
-- If students has 5 rows and departments has 3 rows → 15 rows
```

---

### 🧠 JOIN Summary Cheat Sheet

```
┌──────────────────┬───────────────────────────────────────────┐
│ JOIN Type        │ Returns                                   │
├──────────────────┼───────────────────────────────────────────┤
│ INNER JOIN       │ Only matching rows from both              │
│ LEFT JOIN        │ ALL left + matching right (NULL if none)  │
│ RIGHT JOIN       │ ALL right + matching left (NULL if none)  │
│ FULL OUTER JOIN  │ ALL from both (NULL where no match)       │
│ SELF JOIN        │ Table with itself                         │
│ CROSS JOIN       │ Cartesian product (every × every)         │
└──────────────────┴───────────────────────────────────────────┘
```

---

## 🧱 PHASE 7: SUBQUERIES (Week 5)
### *"Queries inside queries — SQL inception"*

```
⏱️ Estimated: 6–8 hours
Priority: 🔴 Very frequently asked in interviews & GATE
```

### Types of Subqueries

| Type | Returns | Used In |
|------|---------|---------|
| **Scalar** | Single value | `WHERE`, `SELECT` |
| **Column** | One column, multiple rows | `WHERE col IN (subquery)` |
| **Row** | One row, multiple columns | Row comparison |
| **Table** | Full table result | `FROM (subquery) AS t` |

```sql
-- 🔹 Scalar Subquery
-- Find employees earning more than average
SELECT name, salary 
FROM employees 
WHERE salary > (SELECT AVG(salary) FROM employees);

-- 🔹 Column Subquery (IN)
-- Find students in departments that have 'Engineering' in name
SELECT name FROM students 
WHERE dept_id IN (
    SELECT dept_id FROM departments 
    WHERE dept_name LIKE '%Engineering%'
);

-- 🔹 Table Subquery (in FROM clause)
-- Find department-wise highest salary
SELECT dept, max_sal 
FROM (
    SELECT dept, MAX(salary) AS max_sal 
    FROM employees 
    GROUP BY dept
) AS dept_max
WHERE max_sal > 100000;

-- 🔹 Correlated Subquery (references outer query — IMPORTANT!)
-- Find employees who earn more than avg salary of THEIR dept
SELECT name, salary, dept 
FROM employees e1
WHERE salary > (
    SELECT AVG(salary) 
    FROM employees e2 
    WHERE e2.dept = e1.dept   -- references outer query!
);
```

### ⚡ Nested vs Correlated

```
┌─────────────────────┬─────────────────────────────┐
│ Nested Subquery     │ Correlated Subquery         │
├─────────────────────┼─────────────────────────────┤
│ Inner runs ONCE     │ Inner runs for EACH outer row│
│ Independent         │ Depends on outer query       │
│ Faster              │ Slower (but more powerful)   │
│ Bottom-up execution │ Top-down execution           │
└─────────────────────┴─────────────────────────────┘
```

---

## 🧱 PHASE 8: ADVANCED FUNCTIONS (Week 5–6)

```
⏱️ Estimated: 6–8 hours
Priority: Mix of 🔴 and 🟡
```

### 📐 Numeric Functions

```sql
SELECT 
    ROUND(3.14159, 2),    -- 3.14
    CEIL(4.2),             -- 5    (rounds UP)
    FLOOR(4.8),            -- 4    (rounds DOWN)
    ABS(-15),              -- 15
    MOD(10, 3),            -- 1    (remainder)
    POWER(2, 10),          -- 1024
    SQRT(144);             -- 12
```

### 📝 String Functions

```sql
SELECT
    CONCAT('Hello', ' ', 'World'),         -- 'Hello World'
    LENGTH('Database'),                     -- 8
    UPPER('hello'),                         -- 'HELLO'
    LOWER('HELLO'),                         -- 'hello'
    SUBSTRING('Database', 1, 4),            -- 'Data'
    REPLACE('Hello World', 'World', 'SQL'), -- 'Hello SQL'
    TRIM('  hello  '),                      -- 'hello'
    LEFT('Database', 4),                    -- 'Data'
    RIGHT('Database', 4),                   -- 'base'
    REVERSE('SQL');                          -- 'LQS'
```

### 📅 Date & Time Functions

```sql
SELECT
    NOW(),                                    -- Current datetime
    CURDATE(),                                -- Current date
    CURTIME(),                                -- Current time
    YEAR('2024-06-15'),                       -- 2024
    MONTH('2024-06-15'),                      -- 6
    DAY('2024-06-15'),                        -- 15
    DATEDIFF('2024-12-31', '2024-01-01'),    -- 365
    DATE_ADD('2024-01-01', INTERVAL 30 DAY), -- 2024-01-31
    DATE_FORMAT(NOW(), '%d-%m-%Y');           -- '15-06-2024'
```

### 🔀 Conditional Functions

```sql
-- CASE — SQL's if-else
SELECT name, salary,
    CASE 
        WHEN salary >= 100000 THEN 'High'
        WHEN salary >= 50000  THEN 'Medium'
        ELSE 'Low'
    END AS salary_category
FROM employees;

-- COALESCE — Returns first non-NULL value
SELECT name, COALESCE(phone, email, 'No Contact') AS contact
FROM employees;

-- NULLIF — Returns NULL if two values are equal
SELECT NULLIF(10, 10);  -- NULL
SELECT NULLIF(10, 20);  -- 10

-- IFNULL (MySQL) / ISNULL
SELECT name, IFNULL(dept, 'Unassigned') AS department
FROM employees;
```

---

## 🧱 PHASE 9: VIEWS & INDEXES (Week 6)

```
⏱️ Estimated: 4–5 hours
```

### 👁️ Views — Virtual Tables 🟡

```sql
-- Create a view (virtual table — doesn't store data)
CREATE VIEW high_earners AS
SELECT name, dept, salary
FROM employees
WHERE salary > 80000;

-- Use it like a normal table
SELECT * FROM high_earners;

-- Modify
CREATE OR REPLACE VIEW high_earners AS
SELECT name, dept, salary, join_date
FROM employees
WHERE salary > 90000;

-- Delete
DROP VIEW high_earners;
```

> 🧒 **ELI5**: A View is like a **saved Instagram filter**. The original photo (data) doesn't change, but you see it differently each time you apply the filter.

### 📇 Indexes — Speed Boost 🔴

```sql
-- Create index (speeds up WHERE and JOIN on this column)
CREATE INDEX idx_dept ON employees(dept);

-- Composite index (for queries filtering on multiple columns)
CREATE INDEX idx_dept_salary ON employees(dept, salary);

-- Unique index
CREATE UNIQUE INDEX idx_email ON employees(email);

-- View indexes
SHOW INDEX FROM employees;

-- Drop index
DROP INDEX idx_dept ON employees;
```

```
When to use indexes:
✅ Columns used frequently in WHERE
✅ Columns used in JOIN conditions
✅ Columns used in ORDER BY
✅ Large tables (millions of rows)

When NOT to use:
❌ Small tables
❌ Columns with many NULLs
❌ Tables with frequent INSERT/UPDATE (index maintenance cost)
❌ Columns with very few distinct values (e.g., gender)
```

---

## 🧱 PHASE 10: TRANSACTIONS & ACID (Week 6–7)
### *"How databases maintain reliability"*

```
⏱️ Estimated: 5–6 hours
Priority: 🔴 — Critical for exams, GATE, and interviews
```

### 🧒 ELI5 — What is a Transaction?

> Think of **UPI payment**: You send ₹500 to a friend.
> Two things MUST happen:
> 1. ₹500 deducted from YOUR account
> 2. ₹500 added to FRIEND's account
>
> If only step 1 happens and step 2 fails — money disappears!
> A **transaction** ensures BOTH happen or NEITHER happens.

### ACID Properties 🔴🔴🔴

```
┌───────────────┬────────────────────────────────────────────┐
│ Property      │ Meaning                                    │
├───────────────┼────────────────────────────────────────────┤
│ Atomicity     │ All or nothing — partial not allowed       │
│ Consistency   │ DB goes from one valid state to another    │
│ Isolation     │ Concurrent transactions don't interfere    │
│ Durability    │ Once committed, data survives crashes      │
└───────────────┴────────────────────────────────────────────┘
```

```sql
-- Transaction example: Bank Transfer
START TRANSACTION;  -- or BEGIN

UPDATE accounts SET balance = balance - 500 WHERE account_id = 'A';
UPDATE accounts SET balance = balance + 500 WHERE account_id = 'B';

-- If everything is fine:
COMMIT;

-- If something went wrong:
ROLLBACK;

-- SAVEPOINT — partial rollback
START TRANSACTION;
UPDATE accounts SET balance = balance - 500 WHERE account_id = 'A';
SAVEPOINT after_debit;
UPDATE accounts SET balance = balance + 500 WHERE account_id = 'B';
-- Oops, error in credit!
ROLLBACK TO after_debit;  -- Only undo the credit, keep the debit
-- Fix and retry...
COMMIT;
```

### Transaction Isolation Levels 🟡

```
┌────────────────────────┬──────────┬────────────────┬───────────┐
│ Isolation Level        │ Dirty    │ Non-Repeatable │ Phantom   │
│                        │ Read     │ Read           │ Read      │
├────────────────────────┼──────────┼────────────────┼───────────┤
│ READ UNCOMMITTED       │ ✅ Yes   │ ✅ Yes         │ ✅ Yes    │
│ READ COMMITTED         │ ❌ No    │ ✅ Yes         │ ✅ Yes    │
│ REPEATABLE READ        │ ❌ No    │ ❌ No          │ ✅ Yes    │
│ SERIALIZABLE           │ ❌ No    │ ❌ No          │ ❌ No     │
└────────────────────────┴──────────┴────────────────┴───────────┘

Higher isolation = More safe, but slower performance
Default in MySQL: REPEATABLE READ
Default in PostgreSQL: READ COMMITTED
```

---

## 🧱 PHASE 11: DATA INTEGRITY & SECURITY (Week 7)

```
⏱️ Estimated: 3–4 hours
Priority: 🟡 Important for DB admin roles, GATE
```

```sql
-- GRANT — Give permissions
GRANT SELECT, INSERT ON database.employees TO 'intern'@'localhost';

-- REVOKE — Take away permissions
REVOKE INSERT ON database.employees FROM 'intern'@'localhost';

-- GRANT ALL
GRANT ALL PRIVILEGES ON database.* TO 'admin'@'localhost';

-- Show grants
SHOW GRANTS FOR 'intern'@'localhost';
```

### DCL vs DDL vs DML vs TCL — Complete Classification 🔴

```
┌──────────────────────┬─────────────────────────────┐
│ Category             │ Commands                     │
├──────────────────────┼─────────────────────────────┤
│ DDL (Definition)     │ CREATE, ALTER, DROP, TRUNCATE│
│ DML (Manipulation)   │ SELECT, INSERT, UPDATE, DELETE│
│ DCL (Control)        │ GRANT, REVOKE                │
│ TCL (Transaction)    │ COMMIT, ROLLBACK, SAVEPOINT  │
└──────────────────────┴─────────────────────────────┘
```

---

## 🧱 PHASE 12: STORED PROCEDURES & FUNCTIONS (Week 7–8)

```
⏱️ Estimated: 5–6 hours
Priority: 🟡 for exams/interviews | 🔴 for backend dev jobs
```

```sql
-- Stored Procedure — reusable SQL block
DELIMITER //
CREATE PROCEDURE GetHighEarners(IN min_salary DECIMAL(10,2))
BEGIN
    SELECT name, dept, salary
    FROM employees
    WHERE salary >= min_salary
    ORDER BY salary DESC;
END //
DELIMITER ;

-- Call it
CALL GetHighEarners(75000);

-- Stored Function — returns a value
DELIMITER //
CREATE FUNCTION GetBonus(salary DECIMAL(10,2)) 
RETURNS DECIMAL(10,2)
DETERMINISTIC
BEGIN
    DECLARE bonus DECIMAL(10,2);
    IF salary > 100000 THEN
        SET bonus = salary * 0.10;
    ELSEIF salary > 50000 THEN
        SET bonus = salary * 0.15;
    ELSE
        SET bonus = salary * 0.20;
    END IF;
    RETURN bonus;
END //
DELIMITER ;

-- Use it
SELECT name, salary, GetBonus(salary) AS bonus FROM employees;
```

### Procedure vs Function

```
┌──────────────┬─────────────────┬─────────────────┐
│ Feature      │ Procedure       │ Function        │
├──────────────┼─────────────────┼─────────────────┤
│ Returns      │ 0 or more values│ Exactly 1 value │
│ Used in SQL  │ CALL statement  │ Inside SELECT   │
│ RETURN stmt  │ Optional        │ Mandatory       │
│ Side effects │ Can modify data │ Should not      │
│ Transaction  │ Can manage      │ Cannot          │
└──────────────┴─────────────────┴─────────────────┘
```

---

## 🧱 PHASE 13: WINDOW FUNCTIONS (Week 8–9)
### *"The secret weapon for analytics — separates juniors from seniors"*

```
⏱️ Estimated: 8–10 hours
Priority: 🔴 for product company interviews | 🟡 for exams
This is where most students give up. DON'T. It's a goldmine.
```

### 🧒 ELI5 — What are Window Functions?

> Normal aggregate (`GROUP BY`) **collapses rows** — 100 rows become 5 groups.
> Window functions **keep all rows** but add computed columns based on a "window" of related rows.
> Like looking through a **sliding window** at your data.

### Core Window Functions

```sql
-- Sample data setup
CREATE TABLE sales (
    id       INT PRIMARY KEY,
    emp_name VARCHAR(50),
    dept     VARCHAR(30),
    amount   INT,
    sale_date DATE
);

INSERT INTO sales VALUES
(1, 'Rahul', 'North', 5000, '2024-01-15'),
(2, 'Priya', 'South', 7000, '2024-01-16'),
(3, 'Rahul', 'North', 3000, '2024-02-10'),
(4, 'Amit',  'North', 8000, '2024-02-15'),
(5, 'Priya', 'South', 4000, '2024-03-01'),
(6, 'Sneha', 'South', 9000, '2024-03-10'),
(7, 'Amit',  'North', 6000, '2024-03-15');
```

### ROW_NUMBER, RANK, DENSE_RANK 🔴

```sql
SELECT 
    emp_name, dept, amount,
    ROW_NUMBER() OVER (ORDER BY amount DESC) AS row_num,
    RANK()       OVER (ORDER BY amount DESC) AS rank_val,
    DENSE_RANK() OVER (ORDER BY amount DESC) AS dense_rank_val
FROM sales;

-- Result:
-- ┌──────────┬───────┬────────┬─────────┬──────┬────────────┐
-- │ emp_name │ dept  │ amount │ row_num │ rank │ dense_rank │
-- ├──────────┼───────┼────────┼─────────┼──────┼────────────┤
-- │ Sneha    │ South │ 9000   │ 1       │ 1    │ 1          │
-- │ Amit     │ North │ 8000   │ 2       │ 2    │ 2          │
-- │ Priya    │ South │ 7000   │ 3       │ 3    │ 3          │
-- │ Amit     │ North │ 6000   │ 4       │ 4    │ 4          │
-- │ Rahul    │ North │ 5000   │ 5       │ 5    │ 5          │
-- │ Priya    │ South │ 4000   │ 6       │ 6    │ 6          │
-- │ Rahul    │ North │ 3000   │ 7       │ 7    │ 7          │
-- └──────────┴───────┴────────┴─────────┴──────┴────────────┘
```

### The Difference (with ties):

```
Values: 90, 85, 85, 80

ROW_NUMBER:  1, 2, 3, 4    ← Always unique, arbitrary for ties
RANK:        1, 2, 2, 4    ← Ties get same rank, next rank SKIPS
DENSE_RANK:  1, 2, 2, 3    ← Ties get same rank, next rank NO SKIP

🎯 Interview favourite: "Find the 2nd highest salary" → Use DENSE_RANK
```

### PARTITION BY — Window within groups

```sql
-- Rank employees WITHIN each department
SELECT 
    emp_name, dept, amount,
    DENSE_RANK() OVER (
        PARTITION BY dept 
        ORDER BY amount DESC
    ) AS dept_rank
FROM sales;

-- This ranks North employees among North,
-- and South employees among South — separately!
```

### 🏆 Classic Interview Question: Nth Highest Salary

```sql
-- Find 2nd highest salary (handles duplicates correctly)
SELECT salary FROM (
    SELECT salary, DENSE_RANK() OVER (ORDER BY salary DESC) AS rnk
    FROM employees
) ranked
WHERE rnk = 2;

-- Find top earner in EACH department
SELECT * FROM (
    SELECT *, DENSE_RANK() OVER (
        PARTITION BY dept ORDER BY salary DESC
    ) AS rnk
    FROM employees
) ranked
WHERE rnk = 1;
```

### LEAD & LAG 🟡

```sql
-- Compare each sale with the PREVIOUS and NEXT sale
SELECT 
    emp_name, amount, sale_date,
    LAG(amount, 1)  OVER (ORDER BY sale_date) AS prev_sale,
    LEAD(amount, 1) OVER (ORDER BY sale_date) AS next_sale,
    amount - LAG(amount, 1) OVER (ORDER BY sale_date) AS change
FROM sales;

-- LAG = look at PREVIOUS row
-- LEAD = look at NEXT row
-- Super useful for "month-over-month growth" type questions
```

### Running Total / Cumulative Sum 🟡

```sql
SELECT 
    emp_name, amount, sale_date,
    SUM(amount) OVER (ORDER BY sale_date) AS running_total,
    AVG(amount) OVER (ORDER BY sale_date) AS running_avg
FROM sales;
```

---

## 🧱 PHASE 14: CTEs & RECURSIVE QUERIES (Week 9)

```
⏱️ Estimated: 4–5 hours
Priority: 🟡 for exams | 🔴 for product company interviews
```

### Common Table Expressions (CTE) — WITH clause

```sql
-- CTE makes complex queries readable
-- Find departments where avg salary > company avg salary

WITH company_avg AS (
    SELECT AVG(salary) AS avg_sal FROM employees
),
dept_avg AS (
    SELECT dept, AVG(salary) AS dept_avg_sal
    FROM employees
    GROUP BY dept
)
SELECT d.dept, d.dept_avg_sal, c.avg_sal AS company_avg
FROM dept_avg d, company_avg c
WHERE d.dept_avg_sal > c.avg_sal;
```

### Recursive CTE (Advanced) 🟢

```sql
-- Generate numbers 1 to 10
WITH RECURSIVE numbers AS (
    SELECT 1 AS n                    -- Base case
    UNION ALL
    SELECT n + 1 FROM numbers       -- Recursive step
    WHERE n < 10                     -- Termination condition
)
SELECT n FROM numbers;

-- Employee hierarchy (Manager → Reports chain)
WITH RECURSIVE emp_hierarchy AS (
    -- Base: CEO (no manager)
    SELECT emp_id, name, manager_id, 1 AS level
    FROM employees WHERE manager_id IS NULL
    
    UNION ALL
    
    -- Recursive: Find reports of each level
    SELECT e.emp_id, e.name, e.manager_id, h.level + 1
    FROM employees e
    JOIN emp_hierarchy h ON e.manager_id = h.emp_id
)
SELECT * FROM emp_hierarchy ORDER BY level;
```

---

## 🧱 PHASE 15: PERFORMANCE OPTIMIZATION (Week 9–10)
### *"Writing correct SQL is step 1. Writing FAST SQL is mastery."*

```
⏱️ Estimated: 5–6 hours
Priority: 🔴 for backend/database roles | 🟡 for general interviews
```

### Query Optimization Techniques

```
┌────┬──────────────────────────────────┬──────────────────────────────────┐
│ #  │ Bad Practice                     │ Optimized                        │
├────┼──────────────────────────────────┼──────────────────────────────────┤
│ 1  │ SELECT *                         │ SELECT only needed columns       │
│ 2  │ No indexes on WHERE columns      │ Create indexes strategically     │
│ 3  │ Subquery in WHERE                │ Use JOIN instead (usually faster)│
│ 4  │ SELECT DISTINCT (as a band-aid)  │ Fix the root cause (duplicates)  │
│ 5  │ Functions on indexed columns     │ Move function to other side      │
│ 6  │ OR conditions                    │ Use UNION or IN                  │
│ 7  │ NOT IN with NULLs               │ Use NOT EXISTS                   │
│ 8  │ Cartesian joins (missing ON)     │ Always specify JOIN condition    │
│ 9  │ SELECT inside loop (N+1 problem) │ Use batch queries / JOINs       │
│ 10 │ No LIMIT on large tables         │ Always paginate                  │
└────┴──────────────────────────────────┴──────────────────────────────────┘
```

### EXPLAIN / EXPLAIN ANALYZE

```sql
-- See how MySQL executes your query
EXPLAIN SELECT * FROM employees WHERE dept = 'Engineering';

-- Look for:
-- type: ALL (bad — full table scan) vs ref/index (good)
-- rows: how many rows scanned
-- key: which index used (NULL = no index!)
-- Extra: "Using index" (good) vs "Using filesort" (could improve)
```

---

## 📅 COMPLETE WEEK-BY-WEEK PLAN

```
┌──────────┬─────────────────────────────────────┬────────────┐
│ Week     │ Topics                               │ Priority   │
├──────────┼─────────────────────────────────────┼────────────┤
│ Week 1   │ Basics, Data Types, DDL              │ 🔴 Critical│
│ Week 2   │ DML, SELECT mastery, WHERE           │ 🔴 Critical│
│ Week 3   │ Aggregates, GROUP BY, HAVING         │ 🔴 Critical│
│ Week 4   │ Constraints, JOINs (Part 1)          │ 🔴 Critical│
│ Week 5   │ JOINs (Part 2), Subqueries           │ 🔴 Critical│
│ Week 6   │ Functions, Views, Indexes             │ 🟡 Important│
│ Week 7   │ Transactions, ACID, Security          │ 🔴 Critical│
│ Week 8   │ Stored Procedures, Window Funcs       │ 🟡 Important│
│ Week 9   │ CTEs, Recursive Queries, Advanced     │ 🟡 Important│
│ Week 10  │ Performance, Optimization, Practice   │ 🟢 Edge    │
└──────────┴─────────────────────────────────────┴────────────┘
```

### ✅ Milestones

```
After Week 3:  You can handle any college exam question
After Week 5:  You can handle service company (TCS/Infosys) SQL rounds  
After Week 7:  You can handle most product company interview SQL
After Week 10: You're interview-ready for backend/data roles
```

---

## 🏋️ PRACTICE PLATFORMS

| Platform | Best For | Link |
|----------|---------|------|
| **LeetCode** (Database section) | 🔴 Interview prep (50 problems = solid) | leetcode.com/problemset/database |
| **HackerRank** (SQL track) | 🔴 Beginner-friendly, badges | hackerrank.com/domains/sql |
| **SQLZoo** | 🟡 Interactive tutorials | sqlzoo.net |
| **Mode Analytics SQL Tutorial** | 🟡 Analytics-style queries | mode.com/sql-tutorial |
| **StrataScratch** | 🟢 Real company interview Qs | stratascratch.com |
| **w3schools SQL** | 🟡 Quick reference + try-it | w3schools.com/sql |

### 🎯 Recommended Problem Count

```
For Service Companies:    30–50 problems
For Product Companies:    80–100 problems  
For Data/Backend roles:   150+ problems
```

---

## 📚 BEST RESOURCES

| Type | Resource | Why |
|------|----------|-----|
| 📺 YouTube (Hindi) | **CodeWithHarry — SQL Playlist** | Beginner-friendly, Hindi |
| 📺 YouTube (Hindi) | **Gate Smashers — DBMS+SQL** | Exam + GATE focused |
| 📺 YouTube (English) | **Programming with Mosh — SQL** | Clean, professional |
| 📺 YouTube (English) | **freeCodeCamp — SQL Full Course** | 4hr comprehensive |
| 📖 Book | **"Database System Concepts" — Korth** | Standard textbook (Ch 3-5) |
| 📖 Book | **"Learning SQL" — Alan Beaulieu** | Practical, easy to read |
| 🆓 Course | **Khan Academy — Intro to SQL** | Great starting point |
| 🆓 Course | **NPTEL — Database Management** | For GATE + university |

---

## 💼 SQL IN INTERVIEWS — What They Ask

### Service Companies (TCS, Infosys, Wipro)
```
→ Basic SELECT, WHERE, JOINs
→ Aggregate queries
→ Simple subqueries
→ DDL vs DML definitions
→ Normalization theory
→ Difficulty: Easy-Medium
```

### Product Companies (Amazon, Microsoft, Flipkart)
```
→ Complex JOINs (multi-table)
→ Window functions (ROW_NUMBER, RANK)
→ CTEs and nested queries
→ "Find Nth highest salary" type problems
→ Schema design for given scenario
→ Query optimization
→ Difficulty: Medium-Hard
```

### Data Roles (Data Analyst, Data Engineer)
```
→ Everything above +
→ Pivot/Unpivot
→ Advanced window functions
→ Performance tuning
→ Real business scenario queries
→ Difficulty: Hard
```

---

## 🎯 TOP 20 MUST-SOLVE SQL PROBLEMS (Interview Gold)

```
1.  Second highest salary
2.  Nth highest salary (using DENSE_RANK)
3.  Find duplicate emails
4.  Employees earning more than their managers
5.  Department-wise highest salary
6.  Consecutive available seats
7.  Customers who never order
8.  Rising temperature (compare with previous day)
9.  Delete duplicate emails (keep one)
10. Rank scores
11. Department top 3 salaries
12. Trips and users (cancellation rate)
13. Exchange seats
14. Tree node type
15. Employees with missing department
16. Monthly active users
17. Cumulative salary
18. Median employee salary
19. Students report by geography (pivot)
20. Running total of sales
```

> All available on **LeetCode Database** section — search by title.

---

