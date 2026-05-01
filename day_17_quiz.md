## 🎓 Daily Quiz (End of Day)

**Instructions:** Choose the best answer for each question.

1.  What does ADO.NET stand for?
    a) Advanced Data Object .NET
    b) ActiveX Data Objects .NET
    c) A-synchronous Data Operation .NET
    d) Application Data Object .NET

2.  What is the purpose of the `SqliteConnection` object?
    a) To represent the SQL query text.
    b) To read the results of a query.
    c) To manage the connection link to the database file.
    d) To create new database tables.

3.  A "Connection String" is...
    a) A SQL query.
    b) A string that tells the application where to find and how to connect to a database.
    c) The name of the `SqliteDataReader` object.
    d) A type of network cable.

4.  What is the purpose of the `using` statement with database objects?
    a) It makes the code run faster.
    b) It's a way to import namespaces.
    c) It automatically ensures the connection and other resources are closed and disposed of correctly.
    d) It is required to write SQL queries.

5.  Which method on a `SqliteConnection` object must be called before executing a command?
    a) `.Start()` b) `.Init()` c) `.Execute()` d) `.Open()`

6.  The `SqliteCommand` object primarily holds...
    a) The connection string and the results.
    b) The SQL query text and the connection object.
    c) The results of the query.
    d) The name of the database table.

7.  Which method on a `SqliteCommand` is used to execute a `SELECT` query and get a reader?
    a) `ExecuteReader()`
    b) `ExecuteNonQuery()`
    c) `ExecuteSelect()`
    d) `ReadData()`

8.  The `SqliteDataReader` provides...
    a) A read-write, bi-directional view of the data.
    b) An in-memory copy of the entire database table.
    c) A forward-only, read-only stream of data from the query results.
    d) A way to update rows directly.

9.  What does the `reader.Read()` method do?
    a) Reads the entire table into memory.
    b) Returns the number of rows.
    c) Reads a single character from the stream.
    d) Attempts to advance to the next row and returns `true` if successful.

10. A `while (reader.Read())` loop is the standard way to...
    a) Open a database connection.
    b) Iterate through the rows of a query result.
    c) Define a SQL command.
    d) Close a database connection.

11. What is the main difference between accessing a column by index (`reader.GetInt32(0)`) vs. by name (`reader.GetInt32(reader.GetOrdinal("ID"))`)?
    a) Accessing by index is faster but more brittle (it breaks if the SQL query changes order).
    b) Accessing by name is faster.
    c) There is no difference.
    d) You can only access by index.

12. A "NuGet Package" in Visual Studio is...
    a) A project template.
    b) A pre-built library of code that you can add to your project.
    c) A visual theme for the editor.
    d) A debugging tool.

13. The `Microsoft.Data.Sqlite` package is an example of a...
    a) Database engine.
    b) Data Provider for ADO.NET.
    c) C# compiler.
    d) UI framework.

14. Why is it important to set "Copy to Output Directory" for the `.db` file?
    a) To create a backup of the database.
    b) To make sure the running application can find the database file in its execution directory.
    c) To encrypt the database file.
    d) To improve query performance.

15. What is the process of converting a database row into a C# object called?
    a) Serialization
    b) Compilation
    c) Mapping or Hydration
    d) Inheritance

16. A good practice for database code is to...
    a) Place it all directly inside UI event handlers like `Button_Click`.
    b) Keep connections open for the entire duration of the application.
    c) Mix UI logic and data access logic together.
    d) Encapsulate it within its own methods or classes (like a Repository).

17. In WPF, what property of a `DataGrid` do you set to display a collection of objects?
    a) `.DataSource` b) `.Content` c) `.ItemsSource` d) `.DataContext`

18. What is a common bug related to database connections?
    a) Opening too many connections at once.
    b) Forgetting to close connections, leading to resource leaks.
    c) Using a connection string that is too long.
    d) Both a and b.

19. `reader.GetInt32()` is used to read which SQL data type?
    a) `TEXT` b) `REAL` c) `INTEGER` d) `BLOB`

20. The primary goal of today's lab was to...
    a) Write complex SQL queries.
    b) Design a WPF user interface.
    c) Move data from a persistent database into C# objects in application memory.
    d) Update and delete records in the database.

---
<details>
  <summary><strong>ANSWER KEY</strong></summary>
  
  1. **b)** ActiveX Data Objects .NET
  2. **c)** To manage the connection link to the database file.
  3. **b)** A string that tells the application where to find and how to connect to a database.
  4. **c)** It automatically ensures the connection and other resources are closed and disposed of correctly.
  5. **d)** `.Open()`
  6. **b)** The SQL query text and the connection object.
  7. **a)** `ExecuteReader()`
  8. **c)** A forward-only, read-only stream of data from the query results.
  9. **d)** Attempts to advance to the next row and returns `true` if successful.
  10. **b)** Iterate through the rows of a query result.
  11. **a)** Accessing by index is faster but more brittle (it breaks if the SQL query changes order).
  12. **b)** A pre-built library of code that you can add to your project.
  13. **b)** Data Provider for ADO.NET.
  14. **b)** To make sure the running application can find the database file in its execution directory.
  15. **c)** Mapping or Hydration
  16. **d)** Encapsulate it within its own methods or classes (like a Repository).
  17. **c)** `.ItemsSource`
  18. **d)** Both a and b.
  19. **c)** `INTEGER`
  20. **c)** Move data from a persistent database into C# objects in application memory.
</details>
