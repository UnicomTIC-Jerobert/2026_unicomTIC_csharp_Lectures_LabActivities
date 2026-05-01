Of course. Let's proceed to **Week 4, Day 4**.

Today's focus is on software architecture and design patterns. We will take all the raw ADO.NET code we've written and refactor it into a clean, reusable, and professional structure using the **Repository Pattern**. This is a crucial step in moving from writing scripts to building maintainable applications.

Here is the complete curriculum for Day 4, following the established structure.

***

# Week 4, Day 4: The Repository Pattern

## 📖 Lecture Notes (1 Hour)

### 1. Introduction: The Problem with Our Current Code
So far, our `Program.cs` and `MainWindow.xaml.cs` files have contained everything: UI logic, user input handling, AND low-level database connection code.

```csharp
// Inside a Button_Click event...
string connectionString = "...";
using (var connection = new SqliteConnection(connectionString))
{
    connection.Open();
    string sql = "INSERT INTO ...";
    using (var command = new SqliteCommand(sql, connection))
    {
        // ... parameter logic ...
        command.ExecuteNonQuery();
    }
}
```
What's wrong with this?
*   **Violates DRY:** If you need to add a product from three different places in your app, you have to copy-paste this entire block of code.
*   **Hard to Maintain:** If you need to change a column name in the database, you have to hunt down every single SQL string in your entire application.
*   **Poor Separation of Concerns:** Your UI code (WPF) should not know or care *how* data is saved. It doesn't need to know about `SqliteConnection` or SQL syntax. Its only job is to display data and capture user events.
*   **Hard to Test:** You can't test your data logic without also running the user interface.

### 2. The Solution: The Repository Pattern
The **Repository Pattern** is a design pattern that separates the data access logic from the rest of the application. It acts as a mediator between your business logic (the main part of your app) and the data source (the database).

**The Core Idea:** Create a class (e.g., `ProductRepository`) whose **only responsibility** is to handle all database operations for a specific entity (e.g., `Product`).

*   **The Rest of Your App:** Knows nothing about SQL, `SqliteConnection`, or databases. It only knows about the `ProductRepository`.
*   **The Repository:** Contains all the `using` blocks, SQL strings, and ADO.NET code. It exposes simple, clean methods to the rest of the app.

### 3. A "Before and After" Comparison

**Before (in UI code-behind):**
```csharp
// Button_Click event
// ... get product data from textboxes ...
string connectionString = "...";
using (var conn = new SqliteConnection(connectionString))
{
    conn.Open();
    // ... all the SQL command, parameter, and execution logic ...
}
```

**After (using the Repository Pattern):**
```csharp
// In the UI code-behind
public class MainWindow : Window
{
    // The UI only knows about the repository, not the database.
    private readonly ProductRepository _repository = new ProductRepository();

    private void AddButton_Click(object sender, RoutedEventArgs e)
    {
        // 1. Get product data from textboxes into a Product object.
        Product newProduct = new Product { ... };

        // 2. Tell the repository to save it.
        _repository.Add(newProduct);

        // 3. Refresh the UI.
        LoadProducts();
    }
}
```
The UI code is now simple, readable, and completely decoupled from the data access technology. We could switch from SQLite to SQL Server by only changing the code inside the `ProductRepository`, and the UI code would not need to be touched.

### 4. Designing a Repository
A typical repository will have methods that map to the CRUD operations:
*   `GetById(int id)`: Returns a single object.
*   `GetAll()`: Returns a `List<T>` of all objects.
*   `Add(T entity)`: Adds a new object to the database.
*   `Update(T entity)`: Updates an existing object.
*   `Delete(int id)`: Deletes an object by its ID.
*   And any other custom query methods you need, like `FindByCategory(string category)`.

The repository hides all the messy implementation details and provides a clean, object-oriented API for the rest of your application to use.

---
