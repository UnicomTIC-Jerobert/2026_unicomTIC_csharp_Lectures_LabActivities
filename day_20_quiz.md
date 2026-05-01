## 🎓 Weekly Review Quiz (End of Day)

**Instructions:** This quiz covers all topics from Week 4. Choose the best answer.

1.  What is the primary purpose of a database?
    a) To perform complex calculations.
    b) To store data persistently.
    c) To design user interfaces.
    d) To execute C# code.

2.  Which SQL command is used to retrieve data?
    a) `INSERT` b) `UPDATE` c) `SELECT` d) `DELETE`

3.  What does ADO.NET provide?
    a) A user interface framework.
    b) A set of libraries for connecting applications to data sources.
    c) A C# compiler.
    d) A database engine.

4.  The `using` statement is crucial when working with database connections because it...
    a) Makes queries faster.
    b) Automatically closes and disposes of the connection.
    c) Is required for writing SQL.
    d) Encrypts the connection.

5.  Which ADO.NET object is used to read the results of a `SELECT` query in a forward-only manner?
    a) `SqliteConnection` b) `SqliteCommand` c) `SqliteDataReader` d) `DataSet`

6.  SQL Injection is a security vulnerability that is best prevented by using...
    a) String concatenation.
    b) `try-catch` blocks.
    c) `if-else` statements.
    d) Parameterized queries.

7.  Which method is used to execute an `INSERT` or `UPDATE` command in ADO.NET?
    a) `ExecuteReader()` b) `ExecuteScalar()` c) `ExecuteNonQuery()` d) `ExecuteUpdate()`

8.  What is the main goal of the Repository Pattern?
    a) To mix UI and data logic together.
    b) To separate data access logic from the rest of the application.
    c) To replace the need for a database.
    d) To make the UI responsible for writing SQL.

9.  In a well-designed application, the WPF code-behind should...
    a) Contain all the SQL strings and connection logic.
    b) Call methods on a repository object to interact with data.
    c) Directly manipulate the database file.
    d) Be empty.

10. A three-tier architecture commonly consists of...
    a) Model, View, Controller.
    b) Presentation, Business Logic, and Data Access Layers.
    c) C#, XAML, and SQL.
    d) UI, Methods, and Variables.

11. To display a `List<Product>` in a WPF `DataGrid`, you set its...
    a) `.Content` property. b) `.ItemsSource` property. c) `.DataContext` property. d) `.Source` property.

12. In the Repository Pattern, if you switch your database from SQLite to SQL Server, where would you make changes?
    a) In the WPF UI code. b) Primarily inside the Repository class. c) In the `Product` model class. d) In the XAML file.

13. The `WHERE` clause in a SQL statement is used to...
    a) Sort the results. b) Filter the rows. c) Join tables. d) Define columns.

14. What does the `ExecuteNonQuery()` method return?
    a) The number of rows affected. b) A `DataReader`. c) `true` or `false`. d) The ID of the new row.

15. What is the correct property setting for a database file in a Visual Studio project to ensure it's available at runtime?
    a) Build Action: Compile
    b) Build Action: Embedded Resource
    c) Copy to Output Directory: Do not copy
    d) Copy to Output Directory: Copy if newer

16. What does `_repository.GetAll()` likely return?
    a) `void` b) `List<Product>` c) `Product` d) `SqliteDataReader`

17. To get the selected object from a `DataGrid`, you use its...
    a) `.SelectedText` property. b) `.SelectedItem` property. c) `.CurrentRow` property. d) `.GetSelection()` method.

18. `separation of concerns` leads to code that is more...
    a) Tightly coupled. b) Monolithic. c) Maintainable and testable. d) Difficult to read.

19. In our `ProductRepository`, the connection string should be...
    a) A public static field.
    b) A private field, encapsulated within the repository.
    c) Defined in the WPF code-behind.
    d) Hard-coded inside every method.

20. The capstone project for this week demonstrates a full...
    a) CRUD application with a persistent data store and a clean architecture.
    b) In-memory collection manager.
    c) Object-oriented inheritance hierarchy.
    d) Set of disconnected Console applications.

---
<details>
  <summary><strong>ANSWER KEY</strong></summary>
  
  1. **b)** To store data persistently.
  2. **c)** `SELECT`
  3. **b)** A set of libraries for connecting applications to data sources.
  4. **b)** Automatically closes and disposes of the connection.
  5. **c)** `SqliteDataReader`
  6. **d)** Parameterized queries.
  7. **c)** `ExecuteNonQuery()`
  8. **b)** To separate data access logic from the rest of the application.
  9. **b)** Call methods on a repository object to interact with data.
  10. **b)** Presentation, Business Logic, and Data Access Layers.
  11. **b)** `.ItemsSource` property.
  12. **b)** Primarily inside the Repository class.
  13. **b)** Filter the rows.
  14. **a)** The number of rows affected.
  15. **d)** Copy to Output Directory: Copy if newer
  16. **b)** `List<Product>`
  17. **b)** `.SelectedItem` property.
  18. **c)** Maintainable and testable.
  19. **b)** A private field, encapsulated within the repository.
  20. **a)** CRUD application with a persistent data store and a clean architecture.
</details>
