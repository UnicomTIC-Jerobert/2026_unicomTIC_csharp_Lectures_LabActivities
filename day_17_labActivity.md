## 💻 Lab Activities (6 Hours)

### **Objective**
To write C# code that connects to a SQLite database, executes `SELECT` queries, and processes the results using `SqliteDataReader` to create and display objects.

### **Activity 1 (~45 mins): Project Setup and NuGet Package**
*   **Concept:** Preparing a C# project for database access.
*   **Task:**
    1.  Create a new Console App `Day16_DataAccess_Console`.
    2.  **Crucially:** Copy the `Inventory.db` file you created yesterday into the root directory of this new project.
    3.  In the Solution Explorer, right-click the `Inventory.db` file, go to Properties, and set **"Copy to Output Directory"** to **"Copy if newer"**. This ensures the database file is available when you run your program.
    4.  Install the necessary NuGet package:
        *   Right-click your project > Manage NuGet Packages...
        *   Go to the "Browse" tab and search for `Microsoft.Data.Sqlite`.
        *   Click on it and click "Install".

### **Activity 2 (~45 mins): Establishing a Connection**
*   **Concept:** Using `SqliteConnection` to connect to the database file.
*   **Task:** In `Program.cs`:
    1.  Add `using Microsoft.Data.Sqlite;` at the top.
    2.  Define your connection string: `string connectionString = "Data Source=Inventory.db";`.
    3.  Create a `using (SqliteConnection ...)` block.
    4.  Inside the `using` block, call `connection.Open();`.
    5.  Add `Console.WriteLine("Connection opened successfully!");`.
    6.  After the `using` block, add `Console.WriteLine("Connection closed.");`.
    7.  Run the program. You should see both messages, proving the connection lifecycle works.

### **Activity 3 (~45 mins): Executing a Simple Query**
*   **Concept:** Using `SqliteCommand` and `SqliteDataReader` to read all data.
*   **Task:**
    1.  Inside your `using` connection block (after `connection.Open()`), create a `SqliteCommand`.
    2.  Set its command text to `SELECT * FROM Products;`.
    3.  Create a `using (SqliteDataReader ...)` block by calling `command.ExecuteReader()`.
    4.  Inside the reader's `using` block, write a `while (reader.Read())` loop.
    5.  For now, inside the loop, just print a message like `"Reading a row..."`.
    6.  Run the program. You should see the message printed once for each row in your database table.

### **Activity 4 (~45 mins): Reading Column Data**
*   **Concept:** Accessing specific data from the `SqliteDataReader` by index and name.
*   **Task:**
    1.  Modify the inside of your `while (reader.Read())` loop from the previous activity.
    2.  **Access by Index:** Get the `ProductID` using `reader.GetInt32(0)` and the `Name` using `reader.GetString(1)`.
    3.  **Access by Name:** Get the `Price` using `reader.GetDouble(reader.GetOrdinal("Price"))` and the `Stock` using `reader.GetInt32(reader.GetOrdinal("Stock"))`.
    4.  Print the details of each product in a nicely formatted string.

### **Activity 5 (~45 mins): Creating Objects from Data**
*   **Concept:** The main goal of data access: converting database rows into C# objects.
*   **Task:**
    1.  Create a `Product.cs` class in your project that matches the columns in your database table (`ProductID`, `Name`, `Price`, `Stock`).
    2.  Create a `List<Product>` before your database connection code.
    3.  Inside your `while (reader.Read())` loop, instead of just printing the data:
        *   Create a `new Product()` object.
        *   Set its properties using the data you read from the `reader`.
        *   Add the newly created object to your `List<Product>`.
    4.  After the connection is closed, use a `foreach` loop to iterate through your `List<Product>` and print the details of each object.

### **Activity 6 (~45 mins): A Reusable "Get All" Method**
*   **Concept:** Refactoring database logic into a reusable method.
*   **Task:**
    1.  Create a new method: `public static List<Product> GetAllProducts()`.
    2.  Move **all** of your database connection, command, and reading logic (Activities 2-5) inside this new method.
    3.  The method should `return` the populated `List<Product>`.
    4.  Your `Main` method should now become very clean. It should just be:
        ```csharp
        List<Product> inventory = GetAllProducts();
        // ... foreach loop to display the inventory ...
        ```

### **Activity 7 (~45 mins): WPF DataGrid Display**
*   **Concept:** Displaying data retrieved from a database in a graphical UI.
*   **WPF:** Create `Day16_DataAccess_WPF`.
    1.  Add your `Product.cs` class.
    2.  Copy your `GetAllProducts()` method into the `MainWindow.xaml.cs`.
    3.  Copy your `Inventory.db` file to the project and set "Copy if newer".
    4.  Install the `Microsoft.Data.Sqlite` NuGet package.
    5.  In the XAML, add a `<DataGrid x:Name="ProductDataGrid" />`.
    6.  In the `MainWindow` constructor (after `InitializeComponent()`), call your `GetAllProducts()` method to get the list of products.
    7.  Set the `DataGrid`'s data source: `ProductDataGrid.ItemsSource = products;`.
    8.  Run the application. The `DataGrid` should automatically generate columns and display all the data from your database!

### **Activity 8 (~15 mins): Git Submission**
*   **Task:** Stage, commit, and push your new Console and WPF projects to GitHub. Use the message: `"Day 16 Labs: Reading Data from SQLite with ADO.NET"`.

---
