## 🎓 Daily Quiz (End of Day)

**Instructions:** Choose the best answer for each question.

1.  What is the primary goal of the Repository Pattern?
    a) To make database queries run faster.
    b) To separate data access logic from the rest of the application.
    c) To automatically generate SQL queries.
    d) To combine UI logic and data logic into one class.

2.  "Separation of Concerns" in software design means...
    a) Every method should be in its own file.
    b) Each part of the application (UI, business logic, data access) should have a distinct responsibility and not interfere with others.
    c) Using `try-catch` blocks for everything.
    d) A `class` should not have more than 5 methods.

3.  Which of the following is a major problem with putting database code directly in a UI event handler?
    a) It violates the DRY (Don't Repeat Yourself) principle if the code is needed elsewhere.
    b) It makes the UI code tightly coupled to the database technology.
    c) It makes the data access logic difficult to test independently.
    d) All of the above.

4.  In the Repository Pattern, the UI (e.g., WPF `MainWindow`) should only interact with...
    a) The `SqliteConnection` object.
    b) The `ProductRepository` object.
    c) The `Product` model class directly.
    d) The SQL query strings.

5.  What does it mean for code to be "tightly coupled"?
    a) The code is well-organized.
    b) Different parts of the code are highly dependent on each other's implementation details.
    c) The code uses a lot of `using` statements.
    d) The code is difficult to read.

6.  A typical repository class would contain which of the following methods?
    a) `GetAll()`, `GetById(int id)`, `Add(T entity)`
    b) `OpenConnection()`, `CloseConnection()`
    c) `UpdateUI()`, `HandleButtonClick()`
    d) `Main()`

7.  If you use the Repository Pattern and later decide to switch from SQLite to SQL Server, which part of your application will need the most significant changes?
    a) The UI code (WPF XAML and code-behind).
    b) The `Product` model class.
    c) The `ProductRepository` class.
    d) The entire application must be rewritten.

8.  What does it mean to "encapsulate" the data access logic?
    a) To expose all the connection and command details to the UI.
    b) To copy and paste the logic everywhere it's needed.
    c) To hide the complex implementation details inside a class (the repository) and provide a simple public interface.
    d) To encrypt the database connection string.

9.  The "business logic" layer of an application is where...
    a) The user interface is defined.
    b) The core rules and processes of the application reside.
    c) The database connections are managed.
    d) The SQL queries are written.

10. Which of the following should NOT be found inside a well-designed Repository class?
    a) A `SqliteConnection` object.
    b) A SQL `INSERT` statement.
    c) A call to `MessageBox.Show("Product Added!");`.
    d) A `List<Product>` being created and returned.

11. What is the return type of a `repository.GetAll()` method?
    a) `SqliteDataReader`
    b) `List<Product>`
    c) `void`
    d) `int`

12. What is the return type of a `repository.Add(Product p)` method?
    a) `Product`
    b) `List<Product>`
    c) `void`
    d) `int` (sometimes it returns the new ID, but `void` is also common).

13. The `readonly` keyword on a field (like `private readonly ProductRepository _repository;`) means...
    a) The field's value can be changed at any time.
    b) The field must be static.
    c) The field can only be assigned a value in the constructor or at declaration.
    d) The field is public.

14. The Repository Pattern helps improve...
    a) Code organization.
    b) Maintainability.
    c) Testability.
    d) All of the above.

15. What is a "design pattern"?
    a) A strict rule that must be followed in C#.
    b) A visual theme for a WPF application.
    c) A general, reusable solution to a commonly occurring problem in software design.
    d) A type of code library you can download.

16. In our lab, the `ProductRepository` acts as a...
    a) Mediator between the UI and the database.
    b) User interface controller.
    c) Model for a single product.
    d) Replacement for the `Product` class.

17. After refactoring to the Repository Pattern, the `Main` method in our console app should contain...
    a) Lots of ADO.NET code.
    b) UI logic and calls to the repository's public methods.
    c) Only the repository's private methods.
    d) Only a single call to `repository.Start()`.

18. If a repository method needs to get a product by its name, what would be a good signature?
    a) `public Product Get(string name)`
    b) `public List<Product> GetByName()`
    c) `public Product GetByName(string name)`
    d) `public string GetProduct(string name)`

19. The "Single Responsibility Principle" states that a class should have...
    a) Only one public method.
    b) Only one private field.
    c) Only one reason to change.
    d) Only one constructor.

20. How does the Repository Pattern support the Single Responsibility Principle?
    a) It gives the repository the single responsibility of data access.
    b) It gives the UI the single responsibility of managing database connections.
    c) It combines all responsibilities into one class.
    d) It doesn't relate to this principle.

---
<details>
  <summary><strong>ANSWER KEY</strong></summary>
  
  1. **b)** To separate data access logic from the rest of the application.
  2. **b)** Each part of the application (UI, business logic, data access) should have a distinct responsibility and not interfere with others.
  3. **d)** All of the above.
  4. **b)** The `ProductRepository` object.
  5. **b)** Different parts of the code are highly dependent on each other's implementation details.
  6. **a)** `GetAll()`, `GetById(int id)`, `Add(T entity)`
  7. **c)** The `ProductRepository` class.
  8. **c)** To hide the complex implementation details inside a class (the repository) and provide a simple public interface.
  9. **b)** The core rules and processes of the application reside.
  10. **c)** A call to `MessageBox.Show("Product Added!");` (This is UI logic).
  11. **b)** `List<Product>`
  12. **d)** `int` (sometimes it returns the new ID, but `void` is also common). (Context: `void` is a perfectly valid and common return type for Add).
  13. **c)** The field can only be assigned a value in the constructor or at declaration.
  14. **d)** All of the above.
  15. **c)** A general, reusable solution to a commonly occurring problem in software design.
  16. **a)** Mediator between the UI and the database.
  17. **b)** UI logic and calls to the repository's public methods.
  18. **c)** `public Product GetByName(string name)`
  19. **c)** Only one reason to change.
  20. **a)** It gives the repository the single responsibility of data access.
</details>
