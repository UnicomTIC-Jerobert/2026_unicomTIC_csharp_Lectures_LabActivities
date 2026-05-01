## 💻 Lab Activities (6 Hours) - Inventory Management Project

### **Objective**
To build a complete, data-driven WPF application that follows the Repository Pattern, allowing users to perform all CRUD (Create, Read, Update, Delete) operations on a persistent SQLite database.

### **Part 1: Project Setup and UI Design (Activities 1-2)**

#### **Activity 1 (~45 mins): Project Scaffolding**
*   **Concept:** Setting up a clean project structure.
*   **Task:**
    1.  Create a new WPF App `Day19_InventoryProject_WPF`.
    2.  Create three folders inside the project: `Models`, `Repositories`, and `Data`.
    3.  Create a `Product.cs` class inside the `Models` folder. Define its properties (`ProductID`, `Name`, `Price`, `Stock`).
    4.  Create an empty `ProductRepository.cs` class inside the `Repositories` folder.
    5.  Copy your `Inventory.db` file into the `Data` folder. In its properties, set **"Copy to Output Directory"** to **"Copy if newer"**.
    6.  Install the `Microsoft.Data.Sqlite` NuGet package.

#### **Activity 2 (~45 mins): Designing the WPF User Interface**
*   **Concept:** Laying out a functional and intuitive UI for CRUD operations.
*   **Task:** In `MainWindow.xaml`, design the full interface. Use a `<Grid>` to organize the layout.
    1.  **Left Column:** A `<DataGrid x:Name="InventoryDataGrid" IsReadOnly="True" SelectionChanged="InventoryDataGrid_SelectionChanged" />`. `IsReadOnly` prevents users from editing directly in the grid.
    2.  **Right Column:** A "Product Details" `<GroupBox>`. Inside, create a form using `<Label>`s and `<TextBox>`es for each product property (`ProductIdTextBox`, `NameTextBox`, etc.). Make the `ProductIdTextBox` read-only (`IsReadOnly="True"`).
    3.  **Button Panel:** Below the form, add buttons: "Add New", "Update", "Delete", and "Clear Form".

---

### **Part 2: Implementing the Backend Logic (Activities 3-6)**

#### **Activity 3 (~60 mins): Implementing the Full `ProductRepository`**
*   **Concept:** Creating the complete data access layer.
*   **Task:**
    1.  Open `ProductRepository.cs`.
    2.  Define the `private readonly string _connectionString = "Data Source=Data/Inventory.db";`.
    3.  Implement all the CRUD methods from yesterday's lab, ensuring they are all secure and use parameterized queries:
        *   `public List<Product> GetAll()`
        *   `public Product GetById(int id)` (You might not need this for the UI, but it's good practice).
        *   `public void Add(Product product)`
        *   `public void Update(Product product)`
        *   `public void Delete(int id)`

#### **Activity 4 (~45 mins): Loading and Refreshing Data**
*   **Concept:** Populating the UI with data from the database.
*   **Task:** In `MainWindow.xaml.cs`:
    1.  Create a private instance of the repository: `private readonly ProductRepository _repository = new ProductRepository();`.
    2.  Create a method `private void RefreshInventoryGrid()`. This method should:
        *   Call `_repository.GetAll()`.
        *   Set `InventoryDataGrid.ItemsSource` to the returned list.
    3.  Call `RefreshInventoryGrid()` from the `MainWindow` constructor (after `InitializeComponent()`) to load the data when the app starts.

#### **Activity 5 (~60 mins): Selecting and Displaying Product Details**
*   **Concept:** Making the UI interactive by linking the `DataGrid` selection to the form.
*   **Task:**
    1.  Implement the `InventoryDataGrid_SelectionChanged` event handler you created in the XAML.
    2.  Inside this method, get the selected item from the `DataGrid`: `Product selectedProduct = (Product)InventoryDataGrid.SelectedItem;`.
    3.  Add a `null` check: `if (selectedProduct != null)`.
    4.  If it's not null, populate the `TextBox`es on the right with the data from the `selectedProduct`'s properties.

#### **Activity 6 (~30 mins): The "Clear Form" Button**
*   **Concept:** Creating a helper method to reset the UI state.
*   **Task:**
    1.  Create a `private void ClearForm()` method. This method should clear all the text in the `TextBox`es and deselect any item in the `DataGrid` (`InventoryDataGrid.SelectedItem = null;`).
    2.  Implement the "Clear Form" button's `Click` event to simply call `ClearForm()`.
    3.  Also call `ClearForm()` at the end of your Add, Update, and Delete methods to provide a good user experience.

---

### **Part 3: Implementing CRUD Operations (Activities 7-10)**

#### **Activity 7 (~30 mins): Implementing the "Add New" Button**
*   **Concept:** Creating a new record.
*   **Task:**
    1.  Implement the "Add New" button's `Click` event.
    2.  Create a `new Product()` object from the data currently in the `TextBox`es. (Remember to parse `Price` and `Stock`).
    3.  Call `_repository.Add(newProduct);`.
    4.  Call `RefreshInventoryGrid()` to show the newly added item.
    5.  Call `ClearForm()`.

#### **Activity 8 (~30 mins): Implementing the "Update" Button**
*   **Concept:** Modifying an existing record.
*   **Task:**
    1.  Implement the "Update" button's `Click` event.
    2.  Create a `new Product()` object from the data in the `TextBox`es. The `ProductID` will come from the (read-only) `ProductIdTextBox`, which was populated when the user selected an item.
    3.  Call `_repository.Update(productToUpdate);`.
    4.  Call `RefreshInventoryGrid()` and `ClearForm()`.

#### **Activity 9 (~30 mins): Implementing the "Delete" Button**
*   **Concept:** Removing a record.
*   **Task:**
    1.  Implement the "Delete" button's `Click` event.
    2.  Get the `ProductID` from the `ProductIdTextBox`. (Remember to parse it to an `int`).
    3.  Call `_repository.Delete(productIdToDelete);`.
    4.  Call `RefreshInventoryGrid()` and `ClearForm()`.

#### **Activity 10 (~15 mins): Final Testing and Git Submission**
*   **Concept:** Ensuring the application is fully functional and submitting the week's work.
*   **Task:**
    1.  Thoroughly test your application. Add products, update them, delete them. Close and reopen the application to ensure the data is persisting correctly.
    2.  Perform the final **Git Submission** for the week.

---
