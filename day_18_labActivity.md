## 💻 Lab Activities (6 Hours)

### **Objective**
To write C# code that securely modifies data in a SQLite database using `INSERT`, `UPDATE`, and `DELETE` commands. To master the use of `ExecuteNonQuery()` and parameterized queries to prevent SQL injection.

### **Setup for All Activities**
*   Create a new Console App `Day17_DataModification_Console`.
*   Copy your `Inventory.db` file to the project and set "Copy to Output Directory" to "Copy if newer".
*   Install the `Microsoft.Data.Sqlite` NuGet package.
*   Add a `Product.cs` class to your project.
*   Copy your `GetAllProducts()` method from yesterday's lab into `Program.cs` so you can easily view the state of the database after each activity.

### **Activity 1 (~40 mins): Simple `INSERT` (The Insecure Way)**
*   **Concept:** Demonstrating why string concatenation is dangerous.
*   **Task:**
    1.  Write a new method `public static void AddProduct_Insecure(string name, double price)`.
    2.  Inside this method, build an `INSERT` SQL string using string concatenation: `string sql = "INSERT INTO Products (Name, Price) VALUES ('" + name + "', " + price + ");";`.
    3.  Open a connection, create a command, and use `ExecuteNonQuery()` to run it.
    4.  In `Main`, call `GetAllProducts()` to show the initial state. Then, call `AddProduct_Insecure("Test Mug", 9.99);`. Finally, call `GetAllProducts()` again to show that the new product was added.
    5.  **Crucially, add a large comment above the method: `// DANGEROUS - FOR DEMONSTRATION ONLY`**.

### **Activity 2 (~45 mins): Secure `INSERT` with Parameters**
*   **Concept:** Rewriting the `INSERT` logic using safe, parameterized queries.
*   **Task:**
    1.  Create a new method `public static void AddProduct_Secure(Product product)`. This method should take a whole `Product` object as a parameter.
    2.  Write the SQL string with placeholders: `string sql = "INSERT INTO Products (Name, Price, Stock) VALUES (@name, @price, @stock);";`.
    3.  Create your `SqliteCommand` object.
    4.  Use `command.Parameters.AddWithValue()` to add values for `@name`, `@price`, and `@stock` from the input `product` object.
    5.  Execute the command using `ExecuteNonQuery()`.
    6.  In `Main`, test this new method by creating a new `Product` object and passing it to `AddProduct_Secure`. Verify the result with `GetAllProducts()`.

### **Activity 3 (~45 mins): Simple `UPDATE` (The Insecure Way)**
*   **Concept:** Demonstrating the danger of string concatenation for `UPDATE` statements.
*   **Task:**
    1.  Write a method `public static void UpdateProductPrice_Insecure(int id, double newPrice)`.
    2.  Build the SQL string using concatenation: `string sql = "UPDATE Products SET Price = " + newPrice + " WHERE ProductID = " + id;`.
    3.  Execute it with `ExecuteNonQuery()`.
    4.  In `Main`, pick an existing product ID, call this method to update its price, and then use `GetAllProducts()` to verify the change.
    5.  Again, add a large comment marking this as **DANGEROUS**.

### **Activity 4 (~45 mins): Secure `UPDATE` with Parameters**
*   **Concept:** Writing a safe, parameterized `UPDATE` command.
*   **Task:**
    1.  Create a new method `public static void UpdateProductPrice_Secure(int id, double newPrice)`.
    2.  Write the SQL string with placeholders: `string sql = "UPDATE Products SET Price = @price WHERE ProductID = @id;";`.
    3.  Create the command and add the values for the `@price` and `@id` parameters.
    4.  Execute the command and verify the result in `Main`.

### **Activity 5 (~45 mins): Secure `DELETE` with Parameters**
*   **Concept:** Writing a safe, parameterized `DELETE` command.
*   **Task:**
    1.  Create a method `public static void DeleteProduct_Secure(int id)`.
    2.  Write the SQL string with a placeholder: `string sql = "DELETE FROM Products WHERE ProductID = @id;";`.
    3.  Create the command, add the value for the `@id` parameter.
    4.  Execute the command.
    5.  In `Main`, choose a product to delete, call this method, and then use `GetAllProducts()` to confirm it has been removed.

### **Activity 6 (~45 mins): Interactive Console UI**
*   **Concept:** Combining all secure methods into an interactive application.
*   **Task:**
    1.  Create a `while(true)` loop in your `Main` method with a menu that allows the user to:
        *   "1. View all products"
        *   "2. Add a new product"
        *   "3. Update a product's price"
        *   "4. Delete a product"
        *   "5. Exit"
    2.  When the user chooses an option, prompt them for the necessary information (e.g., "Enter new product name:"), and then call the appropriate **secure** method you created (`AddProduct_Secure`, etc.).
    3.  After each action, call `GetAllProducts()` to show the user the updated state of the inventory.

### **Activity 7 (~45 mins): WPF Data Modification UI**
*   **Concept:** Connecting a graphical UI to data modification logic.
*   **WPF:** Create `Day17_DataModification_WPF`.
    1.  Copy your `Product.cs`, `Inventory.db`, and all your **secure** data access methods from the Console project into `MainWindow.xaml.cs`. Install the NuGet package.
    2.  Design a UI with:
        *   A `DataGrid` to display the products.
        *   `TextBox`es for `ID`, `Name`, `Price`, and `Stock`.
        *   Buttons: "Add Product", "Update Price", "Delete Product".
        *   A "Refresh List" button.
    3.  Implement the "Add Product" button. It should create a `new Product` object from the text boxes and call your `AddProduct_Secure` method.
    4.  Implement the "Update Price" button. It should get the `ID` and new `Price` from the text boxes and call `UpdateProductPrice_Secure`.
    5.  Implement the "Delete Product" button. It should get the `ID` from its text box and call `DeleteProduct_Secure`.
    6.  The "Refresh List" button should call `GetAllProducts()` and update the `DataGrid.ItemsSource`. Call this after every modification.

### **Activity 8 (~10 mins): Git Submission**
*   **Task:** Stage, commit, and push your new projects to GitHub with the message: `"Day 17 Labs: Secure CUD Operations with Parameters"`.

---
