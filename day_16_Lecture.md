# Week 4, Day 1: Introduction to SQL and Databases

## 📖 Lecture Notes (1 Hour)

### 1. Introduction: What Happens When Your Program Closes?
So far, all the data our applications have used (in variables, lists, dictionaries) has been stored in the computer's **RAM (Random Access Memory)**. RAM is **volatile**, meaning its contents are erased when the program closes or the computer turns off.

To build real applications, we need **persistence**—a way to save data permanently. The most common and powerful way to do this is with a **Database**.

### 2. What is a Relational Database?
A relational database is a structured way of storing data that uses tables, columns, and rows. Think of it like a collection of highly organized spreadsheets that can be linked to each other.

*   **Table:** Represents a type of entity (e.g., `Students`, `Products`, `Orders`).
*   **Column (or Field):** Represents an attribute of that entity (e.g., `FirstName`, `Price`, `OrderDate`). Each column has a specific data type (`INTEGER`, `TEXT`, `REAL`).
*   **Row (or Record):** Represents a single instance of that entity (e.g., one specific student, one particular product).
*   **Primary Key:** A special column (usually an integer) that has a **unique** value for every single row. This is the main identifier for a record. It cannot be `NULL`.

### 3. Introducing SQLite
There are many types of database systems (SQL Server, MySQL, PostgreSQL), but for learning and for many applications, **SQLite** is perfect.
*   **Serverless:** It's not a separate program that needs to be running.
*   **File-Based:** The entire database (all tables, columns, and rows) is stored in a single `.db` or `.sqlite` file on your computer.
*   **Lightweight and Fast:** It's incredibly efficient and used in countless applications, including web browsers and mobile phones.

### 4. SQL: The Language of Databases
**SQL (Structured Query Language)**, often pronounced "sequel", is the universal language used to communicate with relational databases. It's a declarative language—you describe *what* you want, and the database figures out *how* to get it.

Today, we will focus on the five core commands, collectively known as **DML (Data Manipulation Language)** and **DDL (Data Definition Language)**.

### 5. The Five Core SQL Commands

**1. `CREATE TABLE` (DDL - Defines the structure)**
This command builds the "spreadsheet"—it defines the table and its columns.
```sql
CREATE TABLE Products (
    ProductID   INTEGER PRIMARY KEY AUTOINCREMENT,
    Name        TEXT NOT NULL,
    Price       REAL NOT NULL,
    Stock       INTEGER DEFAULT 0
);
```
*   `INTEGER PRIMARY KEY AUTOINCREMENT`: A special type for an ID that will automatically generate a new unique number for each new row.
*   `TEXT`, `REAL`, `INTEGER`: Common SQLite data types.
*   `NOT NULL`: A constraint that says this column must have a value.

**2. `INSERT INTO` (DML - Adds new rows)**
This command adds a new record to a table.
```sql
INSERT INTO Products (Name, Price, Stock) 
VALUES ('Laptop', 1200.50, 15);

INSERT INTO Products (Name, Price) 
VALUES ('Coffee Mug', 12.00); -- Stock will be 0 because of the DEFAULT
```

**3. `SELECT` (DML - Retrieves rows)**
This is the most powerful and common command. It's used to query and read data.
```sql
-- Get ALL columns from ALL rows in the Products table
SELECT * FROM Products;

-- Get only the Name and Price columns
SELECT Name, Price FROM Products;

-- Get products that match a specific condition
SELECT * FROM Products WHERE Price > 100;

-- Get products and sort them by name
SELECT * FROM Products ORDER BY Name ASC; -- ASC for ascending, DESC for descending
```

**4. `UPDATE` (DML - Modifies existing rows)**
This command changes data in rows that already exist. **Warning: Always use a `WHERE` clause with `UPDATE`, or you will change every row in the table!**
```sql
UPDATE Products
SET Stock = 20, Price = 1150.00
WHERE ProductID = 1; -- Update the product with ID 1
```

**5. `DELETE` (DML - Removes rows)**
This command removes records from a table. **Warning: Always use a `WHERE` clause with `DELETE`!**
```sql
DELETE FROM Products
WHERE ProductID = 2; -- Delete the product with ID 2
```

---
