### 🏛️ Big Picture Overview
- **Where Oracle SQL fits:**  
  Oracle SQL is used to interact with Oracle databases. It's used for storing, manipulating, and querying relational data. SQL (Structured Query Language) enables data retrieval, updates, and the management of database schemas, tables, views, and other database objects. It's essential in **backend development** for interacting with relational databases and is widely used in enterprise-level applications.

- **Connection with Other Systems:**  
  Oracle SQL interacts directly with **backend applications** written in languages like **Java**, **Spring Boot**, or **Python** to handle data persistence and retrieval. It can be linked with **business logic** on the server-side through **Stored Procedures**, **Triggers**, and **Views** that enhance the performance and scalability of applications.

- **Typical Architecture Diagram:**
  ```
  [User (Application)] → [Backend (Java/Spring)] → [Oracle SQL Database] → [Queries/Stored Procedures]
  ```

---

### 🧩 Modular Breakdown
| Module                        | Sub-Feature Areas                             | Real-World Context                                      |
|-------------------------------|-----------------------------------------------|---------------------------------------------------------|
| **SELECT Queries**             | Basic SELECT, WHERE, ORDER BY, DISTINCT       | Extracting data from tables with filtering and sorting |
| **Joins**                      | INNER JOIN, LEFT JOIN, RIGHT JOIN, FULL JOIN  | Combining data from multiple tables for complex queries |
| **Stored Procedures**          | Creating, Executing, Returning Results        | Predefined queries to encapsulate business logic and reuse |
| **Views**                       | Creating Views, Updating Views                | Virtual tables for abstracting complex joins or queries |
| **Transactions**               | COMMIT, ROLLBACK, SAVEPOINT                   | Ensuring data integrity by grouping related queries |
| **SQL Tuning**                 | EXPLAIN PLAN, Indexing, Optimizing Queries    | Improving query performance to handle large datasets |
| **Backup/Recovery**            | RMAN, Data Pump, Export/Import               | Ensuring database availability and disaster recovery |
| **Security**                   | Granting Permissions, User Roles              | Restricting access to sensitive data and operations |

---

### 🧠 Mind Map

```
Oracle SQL
├── SELECT Queries
│   ├── Basic SELECT
│   ├── WHERE
│   ├── ORDER BY
│   └── DISTINCT
├── Joins
│   ├── INNER JOIN
│   ├── LEFT JOIN
│   ├── RIGHT JOIN
│   └── FULL JOIN
├── Stored Procedures
│   ├── Creating Stored Procedures
│   ├── Executing Stored Procedures
│   └── Returning Results
├── Views
│   ├── Creating Views
│   ├── Updating Views
│   └── Using Views
├── Transactions
│   ├── COMMIT
│   ├── ROLLBACK
│   └── SAVEPOINT
├── SQL Tuning
│   ├── EXPLAIN PLAN
│   ├── Indexing
│   └── Query Optimization
├── Backup/Recovery
│   ├── RMAN
│   ├── Data Pump
│   └── Export/Import
└── Security
    ├── Granting Permissions
    ├── User Roles
    └── Restricting Access
```

---

### 🧠 Key Technical Words & Definitions
| Term                      | Definition |
|---------------------------|------------|
| **SELECT**                 | A SQL command used to retrieve data from one or more tables in a database. |
| **JOIN**                   | A SQL operation that combines data from two or more tables based on a related column. |
| **Stored Procedure**       | A precompiled SQL query that can be executed with a single call, improving performance and reusability. |
| **View**                   | A virtual table in SQL created by a query. Views do not store data but represent the results of a SELECT query. |
| **Transaction**            | A sequence of SQL statements executed as a single unit of work, ensuring data integrity with COMMIT and ROLLBACK. |
| **SQL Tuning**             | The process of optimizing SQL queries for faster performance, often involving indexing and query refactoring. |
| **Backup/Recovery**        | Methods to create a backup of the database and restore it in case of failure, ensuring data is not lost. |
| **Security**               | The practice of controlling access to data and operations using permissions and roles in the database. |

---

### ❓ Common Interview Questions
- What is a **JOIN** in SQL and how does it differ from a **SUBQUERY**?
- How would you improve the performance of a slow-running query?
- Explain the differences between **INNER JOIN**, **LEFT JOIN**, **RIGHT JOIN**, and **FULL JOIN**.
- What is the purpose of **SQL transactions** and how do **COMMIT**, **ROLLBACK**, and **SAVEPOINT** work?
- How do you create and use **Stored Procedures** in Oracle SQL?
- What is the significance of using **indexes** in SQL queries?
- How do you perform **backup** and **recovery** of an Oracle database?
- How do you manage **user permissions** in Oracle SQL?

---

### 🔥 Code Snippets

```sql
-- Example: SELECT Query
SELECT employee_id, first_name, last_name
FROM employees
WHERE department_id = 90
ORDER BY last_name;

-- Example: INNER JOIN
SELECT e.first_name, e.last_name, d.department_name
FROM employees e
INNER JOIN departments d
ON e.department_id = d.department_id;

-- Example: Stored Procedure
CREATE PROCEDURE GetEmployeeByDepartment (IN dept_id INT)
BEGIN
   SELECT first_name, last_name FROM employees WHERE department_id = dept_id;
END;

-- Example: Transaction
BEGIN;
UPDATE employees SET salary = salary * 1.1 WHERE department_id = 90;
COMMIT;

-- Example: Indexing
CREATE INDEX idx_employee_last_name ON employees(last_name);
```

---

### 🎯 Best Practices Summary
- **Use Indexed Columns for Joins:** Ensure that columns used in JOIN conditions are indexed to improve query performance.
- **Use Stored Procedures for Repeated Operations:** Group commonly used SQL operations into stored procedures for better maintainability and reusability.
- **Keep Queries Simple:** Avoid writing overly complex queries that are hard to debug or maintain.
- **Monitor and Optimize SQL Performance:** Regularly monitor SQL queries using **EXPLAIN PLAN** and optimize slow queries with indexing or query adjustments.

---

### ⚡ Cheat Sheet Summary
| Concept                     | Shortcut/Tip |
|------------------------------|--------------|
| **JOIN**                     | Use appropriate joins (`INNER`, `LEFT`, `RIGHT`, `FULL`) based on the need to combine tables. |
| **Transactions**              | Always ensure data integrity using **COMMIT** and **ROLLBACK**. |
| **Stored Procedures**         | Encapsulate repetitive tasks in stored procedures to improve code reusability. |
| **SQL Tuning**                | Always examine query performance with **EXPLAIN PLAN** and optimize slow-running queries. |

---

### 🧑‍🏫 Learning Resources
- **Oracle SQL Documentation:** [Oracle SQL Docs](https://docs.oracle.com/en/database/oracle/sql/)
- **SQLZoo:** [SQLZoo](https://sqlzoo.net/)
- **LeetCode SQL Practice:** [LeetCode SQL](https://leetcode.com/problemset/database/)
  
---

Now let's proceed with **PL/SQL**.

---

## 02-TechSkill/Database-PLSQL.md

### 🏛️ Big Picture Overview
- **Where PL/SQL fits:**  
  PL/SQL is Oracle's procedural extension to SQL, allowing for complex logic and control structures. While SQL is great for simple data queries, PL/SQL enables developers to create procedures, functions, and triggers to manage data more efficiently, especially for business logic operations.

- **Connection with Other Systems:**  
  PL/SQL interacts with **Oracle SQL** and is used to manage complex transactions, handle errors, and process data in a procedural manner. It is often used alongside **Java** or **Spring Boot** in backend systems where business logic needs to be executed before or after data manipulation.

- **Typical Architecture Diagram:**
  ```
  [User (Application)] → [Backend (Java/Spring)] → [PL/SQL Procedures] → [Oracle Database]
  ```

---

### 🧩 Modular Breakdown
| Module                        | Sub-Feature Areas                             | Real-World Context                                      |
|-------------------------------|-----------------------------------------------|---------------------------------------------------------|
| **PL/SQL Basics**              | Blocks, Cursors, Variables                   | Writing basic procedures and functions for modular logic |
| **Error Handling**             | Exception Handling, Named Exceptions          | Managing errors to ensure data consistency and robustness |
| **Triggers**                   | BEFORE/AFTER, DML Triggers, Event Triggers    | Automatically executing actions before or after a database event |
| **Packages**                   | Creating and Using Packages, Modularization   | Grouping related PL/SQL objects (functions, procedures) |
| **Advanced PL/SQL**            | Bulk Collect, FORALL                         | Optimizing PL/SQL performance for handling large data sets |

---

### 🧠 Mind Map

```
PL/SQL
├── PL/SQL Basics
│   ├── Blocks
│   ├── Cursors
│   └── Variables
├── Error Handling
│   ├── Exception Handling
│   ├── Named Exceptions
│   └── Custom Exceptions
├── Triggers
│   ├── BEFORE/AF

TER
│   ├── DML Triggers
│   └── Event Triggers
├── Packages
│   ├── Creating Packages
│   ├── Using Packages
│   └── Modularization
├── Advanced PL/SQL
│   ├── Bulk Collect
│   ├── FORALL
│   └── Optimizing Performance
```

---

### 🧠 Key Technical Words & Definitions
| Term                      | Definition |
|---------------------------|------------|
| **Block**                  | A PL/SQL block consists of three sections: declaration, execution, and exception handling. |
| **Cursor**                 | A pointer used to retrieve data row by row in PL/SQL. |
| **Trigger**                | A PL/SQL block of code that is automatically executed in response to specific events in the database. |
| **Package**                | A collection of related PL/SQL procedures and functions that are grouped together for modularization. |
| **FORALL**                 | A PL/SQL feature that allows bulk inserts or updates to be performed more efficiently. |
| **Bulk Collect**           | A method for retrieving large amounts of data into collections in PL/SQL. |
| **Exception Handling**     | The process of catching and handling errors during PL/SQL execution to maintain system stability. |

---

### ❓ Common Interview Questions
- What is the difference between **PL/SQL blocks** and **anonymous blocks**?
- How do you manage **exceptions** in PL/SQL?
- What are **Triggers** and how do they work?
- How does **FORALL** improve PL/SQL performance?
- How do you implement **Bulk Collect** in PL/SQL?

---

### 🔥 Code Snippets

```sql
-- Example: Basic PL/SQL Block
DECLARE
   v_emp_name VARCHAR2(50);
BEGIN
   SELECT first_name INTO v_emp_name FROM employees WHERE employee_id = 101;
   DBMS_OUTPUT.PUT_LINE('Employee Name: ' || v_emp_name);
END;

-- Example: PL/SQL Cursor
DECLARE
   CURSOR emp_cursor IS SELECT employee_id, first_name FROM employees;
   v_employee employees.employee_id%TYPE;
BEGIN
   OPEN emp_cursor;
   LOOP
      FETCH emp_cursor INTO v_employee;
      EXIT WHEN emp_cursor%NOTFOUND;
      DBMS_OUTPUT.PUT_LINE('Employee ID: ' || v_employee);
   END LOOP;
   CLOSE emp_cursor;
END;

-- Example: Trigger
CREATE OR REPLACE TRIGGER emp_salary_update
BEFORE UPDATE OF salary ON employees
FOR EACH ROW
BEGIN
   IF :new.salary < :old.salary THEN
      RAISE_APPLICATION_ERROR(-20001, 'Salary cannot be reduced');
   END IF;
END;

-- Example: Package
CREATE OR REPLACE PACKAGE emp_package AS
   PROCEDURE get_employee_by_id (emp_id IN NUMBER);
END emp_package;
```

---

### 🎯 Best Practices Summary
- **Use Cursors Efficiently:** Always close cursors after use to avoid memory leaks.
- **Exception Handling:** Always handle exceptions to prevent program crashes and ensure graceful handling of errors.
- **Trigger Management:** Be mindful of recursive triggers and performance impacts, as triggers can significantly affect DML operations.

---

### ⚡ Cheat Sheet Summary
| Concept                     | Shortcut/Tip |
|------------------------------|--------------|
| **PL/SQL Block**              | Declare variables, use exceptions to catch errors, and use **DBMS_OUTPUT** for debugging. |
| **Cursor**                    | Use cursors for row-by-row processing but avoid them in favor of bulk operations when possible. |
| **Triggers**                  | Ensure **BEFORE** triggers are used for validations and **AFTER** triggers for logging. |
| **Bulk Operations**           | Use **FORALL** and **Bulk Collect** for better performance in handling large datasets. |

---

### 🧑‍🏫 Learning Resources
- **PL/SQL Documentation:** [PL/SQL Docs](https://docs.oracle.com/en/database/oracle/plsql/)
- **Oracle PL/SQL Tutorial:** [PL/SQL Tutorial](https://www.tutorialspoint.com/plsql/index.htm)
- **PL/SQL Examples:** [PL/SQL Examples](https://www.oracle.com/database/technologies/plsql.html)

---

Next, I will continue with **MySQL**. Would you like me to proceed?
