## 💻 Lab Activities (6 Hours)

### **Objective**
To refactor raw ADO.NET code into a well-structured `Repository` class, demonstrating a clear separation of concerns between data access logic and application/UI logic.

### **Activity 1 (~45 mins): Project Setup and Scaffolding**
*   **Concept:** Preparing the project structure for the repository pattern.
*   **Task:**
    1.  Create a new Console App `Day18_RepositoryPattern_Console`.
    2.  Copy your `Inventory.db` and `Product.cs` files into the project. Set "Copy if newer".
    3.  Install the `Microsoft.Data.Sqlite` NuGet package.
    4.  Create a new, empty class file named `ProductRepository.cs`.
    5.  Inside `ProductRepository.cs`, add a private field for the connection string: `private readonly string _connectionString = "Data Source=Inventory.db";`.

### **Activity 2 (~45 mins): Refactoring the `GetAll` Method**
*   **Concept:** Moving the data retrieval logic into the repository.
*   **Task:**
    1.  Find your `GetAllProducts()` method from yesterday's lab.
    2.  Copy the entire method into your new `ProductRepository.cs` class.
    3.  Rename it to `public List<Product> GetAll()`.
    4.  Make sure the method uses the `_connectionString` field you created.
    5.  In `Program.cs`, create an instance of your new repository: `ProductRepository repo = new ProductRepository();`.
    6.  Call `repo.GetAll()` and loop through the results to prove it works. Your `Main` method should no longer contain any ADO.NET code.

### **Activity 3 (~45 mins): Creating the `GetById` Method**
*   **Concept:** Implementing a repository method that takes a parameter for a `WHERE` clause.
*   **Task:**
    1.  In `ProductRepository.cs`, create a `public Product GetById(int id)` method.
    2.  Inside, write the ADO.NET logic for a `SELECT` query with a `WHERE ProductID = @id` clause.
    3.  Use parameterized queries for the `id`.
    4.  Your `while (reader.Read())` loop will only run once (or not at all). Create and return the `Product` object. If no product is found, return `null`.
    5.  In `Program.cs`, test this method by asking the user for an ID and displaying the result.

### **Activity 4 (~45 mins): Refactoring the `Add` Method**
*   **Concept:** Moving the `INSERT` logic into the repository.
*   **Task:**
    1.  Find your `AddProduct_Secure` method from yesterday.
    2.  Copy its logic into a new method in `ProductRepository.cs` called `public void Add(Product product)`.
    3.  Ensure it uses parameterized queries and the `_connectionString` field.
    4.  In `Program.cs`, test this by creating a new `Product` object and calling `repo.Add(myNewProduct);`.

### **Activity 5 (~45 mins): Refactoring `Update` and `Delete`**
*   **Concept:** Completing the CRUD implementation in the repository.
*   **Task:**
    1.  In `ProductRepository.cs`, create a `public void Update(Product product)` method. Copy your secure `UPDATE` logic into it. This method should update all fields based on the product's ID.
    2.  In `ProductRepository.cs`, create a `public void Delete(int id)` method. Copy your secure `DELETE` logic into it.
    3.  In `Program.cs`, write test code to verify that you can update a product's price and delete another product by calling the repository methods.

### **Activity 6 (~45 mins): The Clean Console UI**
*   **Concept:** Building a UI that is completely decoupled from the data layer.
*   **Task:**
    1.  Delete all the test code from your `Program.cs` `Main` method.
    2.  Re-implement the interactive menu from yesterday's lab.
    3.  Crucially, every single database operation must now be a simple, one-line call to a method on your `ProductRepository` instance (e.g., `repo.GetAll()`, `repo.Delete(idToDelete)`, etc.).
    4.  Confirm that there is **zero** ADO.NET or SQL code left in your `Program.cs` file.

### **Activity 7 (~45 mins): WPF with the Repository Pattern**
*   **Concept:** Applying the repository pattern to a graphical user interface.
*   **WPF:** Create `Day18_RepositoryPattern_WPF`.
    1.  Add `Product.cs`, `ProductRepository.cs`, and `Inventory.db` to the project. Install the NuGet package and set "Copy if newer".
    2.  In `MainWindow.xaml.cs`, create a private instance of the repository: `private readonly ProductRepository _repository = new ProductRepository();`.
    3.  Re-build the WPF UI from yesterday (DataGrid, TextBoxes, Buttons for Add/Update/Delete).
    4.  Refactor every single button's `Click` event handler to use the `_repository` instance, just like you did in the Console UI. For example, the "Add" button should create a `Product` object and then simply call `_repository.Add(newProduct);`.
    5.  Ensure there is **zero** ADO.NET or SQL code in your `MainWindow.xaml.cs`.

### **Activity 8 (~15 mins): Git Submission**
*   **Task:** Stage, commit, and push your new, well-structured projects to GitHub. Use the message: `"Day 18 Labs: Refactored to Repository Pattern"`.

---
