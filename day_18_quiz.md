## 🎓 Daily Quiz (End of Day)

**Instructions:** Choose the best answer for each question.

1.  Which method is used to execute `INSERT`, `UPDATE`, and `DELETE` commands?
    a) `ExecuteReader()`
    b) `ExecuteQuery()`
    c) `ExecuteNonQuery()`
    d) `ExecuteScalar()`

2.  What does `ExecuteNonQuery()` return?
    a) A `SqliteDataReader`.
    b) A boolean indicating success or failure.
    c) The number of rows affected by the command.
    d) Nothing (`void`).

3.  What is SQL Injection?
    a) A technique to make SQL queries run faster.
    b) A security vulnerability where malicious SQL code is inserted into a query.
    c) A way to connect C# to a database.
    d) A type of database error.

4.  Why is building SQL queries with string concatenation dangerous?
    a) It is slow.
    b) It can lead to syntax errors.
    c) It opens the door to SQL Injection attacks if user input is involved.
    d) It uses too much memory.

5.  What is the secure, professional way to include user data in SQL queries?
    a) By using `string.Format()`.
    b) By using string concatenation (`+`).
    c) By using parameterized queries.
    d) By encrypting the user input first.

6.  In a parameterized query, placeholders in the SQL string typically start with what character?
    a) `?` b) `$` c) `%` d) `@`

7.  Which line correctly adds a parameter to a `SqliteCommand`?
    a) `command.Parameters.Add("@name", name);`
    b) `command.Parameters.AddWithValue("@name", name);`
    c) `command.AddParameter("@name", name);`
    d) Both a and b are common ways.

8.  The main benefit of parameterized queries is that they...
    a) Treat user input as pure data, never as executable SQL code.
    b) Are easier to write than concatenated strings.
    c) Automatically open and close the database connection.
    d) Can execute multiple commands at once.

9.  For which SQL command would you use `ExecuteReader()`?
    a) `INSERT` b) `UPDATE` c) `DELETE` d) `SELECT`

10. For which SQL command would you use `ExecuteNonQuery()`?
    a) `SELECT`
    b) `INSERT`
    c) `UPDATE`
    d) All of b and c.

11. A `DELETE FROM Products;` command (without a `WHERE` clause) will...
    a) Delete the first row.
    b) Delete the entire table structure.
    c) Delete all rows from the table.
    d) Cause a syntax error.

12. The `command.Parameters` property is a collection of...
    a) SQL query strings.
    b) `SqliteParameter` objects.
    c) Connection strings.
    d) Data readers.

13. What is wrong with this code? `string sql = "SELECT * FROM Users WHERE Name = '" + userName + "';";`
    a) Nothing is wrong.
    b) It is vulnerable to SQL Injection.
    c) It is missing an `ORDER BY` clause.
    d) It will not compile.

14. When using parameterized queries, do you need to add single quotes around string placeholders in the SQL text? (e.g., `VALUES ('@name')`)
    a) Yes, always.
    b) No, the database driver handles the quoting.
    c) Only for `UPDATE` statements.
    d) Only if the string contains spaces.

15. If an `UPDATE` statement affects 0 rows, what will `ExecuteNonQuery()` return?
    a) `0` b) `-1` c) `null` d) It will throw an exception.

16. What is the purpose of the `Product` class in our lab?
    a) To manage the database connection.
    b) To represent a single row of data from the `Products` table as a C# object.
    c) To execute SQL queries.
    d) To define the user interface.

17. In a secure `UPDATE` statement, what parts should be parameterized?
    a) Only the values in the `SET` clause.
    b) Only the values in the `WHERE` clause.
    c) Both the values in the `SET` and `WHERE` clauses.
    d) The table name and column names.

18. What is the first step in adding a new product securely?
    a) Open the database connection.
    b) Create a `Product` object in C#.
    c) Write the `INSERT` statement with placeholders.
    d) Get the user input.

19. Why do we still need a `using` block for `ExecuteNonQuery()` commands?
    a) To ensure the command object is disposed.
    b) To ensure the connection is always closed, even if the command fails.
    c) To catch SQL exceptions.
    d) It's not strictly necessary, but good practice.

20. The most important lesson of today is to...
    a) Learn the `INSERT` syntax.
    b) Always use `ExecuteNonQuery()` for `UPDATE` commands.
    c) Never trust user input and always use parameterized queries to prevent SQL Injection.
    d) Know how to delete records from a database.

---
<details>
  <summary><strong>ANSWER KEY</strong></summary>
  
  1. **c)** `ExecuteNonQuery()`
  2. **c)** The number of rows affected by the command.
  3. **b)** A security vulnerability where malicious SQL code is inserted into a query.
  4. **c)** It opens the door to SQL Injection attacks if user input is involved.
  5. **c)** By using parameterized queries.
  6. **d)** `@`
  7. **d)** Both a and b are common ways. (`AddWithValue` is a convenient shortcut).
  8. **a)** Treat user input as pure data, never as executable SQL code.
  9. **d)** `SELECT`
  10. **d)** All of b and c.
  11. **c)** Delete all rows from the table.
  12. **b)** `SqliteParameter` objects.
  13. **b)** It is vulnerable to SQL Injection.
  14. **b)** No, the database driver handles the quoting.
  15. **a)** `0`
  16. **b)** To represent a single row of data from the `Products` table as a C# object.
  17. **c)** Both the values in the `SET` and `WHERE` clauses.
  18. **c)** Write the `INSERT` statement with placeholders.
  19. **b)** To ensure the connection is always closed, even if the command fails.
  20. **c)** Never trust user input and always use parameterized queries to prevent SQL Injection.
</details>
