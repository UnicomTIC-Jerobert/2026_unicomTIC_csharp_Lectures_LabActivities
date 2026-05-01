## 💻 Lab Activities (6 Hours)

### **Objective**
To gain hands-on experience with database structure and the SQL language. By the end of the day, you will be able to create tables and perform all CRUD (Create, Read, Update, Delete) operations using raw SQL in a database management tool.

### **Software Installation (~30 mins)**
*   **Tool:** DB Browser for SQLite.
*   **Task:**
    1.  Go to [https://sqlitebrowser.org/dl/](https://sqlitebrowser.org/dl/).
    2.  Download and install the appropriate version for your operating system (Windows or macOS). This is a simple, portable tool that lets us work with SQLite files directly.

### **Activity 1 (~45 mins): Creating Your First Database and Table**
*   **Concept:** Database and table creation (DDL).
*   **Task:**
    1.  Open DB Browser for SQLite.
    2.  Click **"New Database"**.
    3.  Save the file in a new project folder for today's work, naming it `Inventory.db`.
    4.  A "Edit table definition" dialog will pop up. You can use this GUI to create a table, but we will use SQL. **Cancel** this dialog.
    5.  Go to the **"Execute SQL"** tab.
    6.  In the SQL editor window, type the `CREATE TABLE` statement for a `Products` table from the lecture notes. Make sure it has `ProductID`, `Name`, `Price`, and `Stock` columns with the correct data types and constraints.
    7.  Click the "Execute" button (or press F5). You should see a "Query executed successfully" message.
    8.  Go back to the **"Database Structure"** tab. You should now see your `Products` table listed. Click on it to see its schema.

### **Activity 2 (~45 mins): Inserting Data (`INSERT`)**
*   **Concept:** Adding new records to a table.
*   **Task:**
    1.  Go back to the **"Execute SQL"** tab.
    2.  Write and execute **five** separate `INSERT INTO` statements to add five different products to your `Products` table.
    3.  Include a variety of prices and stock levels. Make one item have 0 stock.
    4.  To verify your work, go to the **"Browse Data"** tab, select your `Products` table from the dropdown, and you should see the five rows you just inserted.

### **Activity 3 (~45 mins): Basic Data Retrieval (`SELECT`)**
*   **Concept:** Querying data using `SELECT`.
*   **Task:** In the **"Execute SQL"** tab, write and execute the following queries one at a time:
    1.  A query to select **all** columns from **all** products.
    2.  A query to select only the `Name` and `Stock` columns for all products.
    3.  A query to select the product with a `ProductID` of 3.

### **Activity 4 (~45 mins): Advanced `SELECT` with `WHERE`**
*   **Concept:** Filtering data based on conditions.
*   **Task:** Write and execute the following queries:
    1.  Select all products where the `Price` is less than 50.
    2.  Select all products where the `Stock` is 0.
    3.  Select all products where the `Name` is exactly 'Laptop' (or one of your product names).
    4.  Select all products where the `Price` is greater than 20 **AND** the `Stock` is greater than 10.

### **Activity 5 (~45 mins): Sorting Results with `ORDER BY`**
*   **Concept:** Ordering the query output.
*   **Task:** Write and execute the following queries:
    1.  Select all products, sorted by `Name` in alphabetical order (`ASC`).
    2.  Select all products, sorted by `Price` from most expensive to least expensive (`DESC`).
    3.  Select all products with more than 5 items in stock, sorted by `Stock` from lowest to highest.

### **Activity 6 (~45 mins): Modifying Data (`UPDATE`)**
*   **Concept:** Changing data in existing records.
*   **Task:**
    1.  Write an `UPDATE` statement to change the `Price` of a single product (use its `ProductID` in the `WHERE` clause).
    2.  Write an `UPDATE` statement to increase the `Stock` of another product by 10 (e.g., `SET Stock = Stock + 10`).
    3.  Go to the **"Browse Data"** tab to verify that your changes were correctly applied.

### **Activity 7 (~45 mins): Removing Data (`DELETE`)**
*   **Concept:** Deleting records from a table.
*   **Task:**
    1.  Write a `DELETE` statement to remove a single product from the table using its `ProductID` in the `WHERE` clause.
    2.  Go to the **"Browse Data"** tab to verify that the row is gone.
    3.  **Challenge:** Write a `DELETE` statement to remove all products that are out of stock (`Stock = 0`).

### **Activity 8 (~15 mins): Git Submission**
*   **Task:** Today's submission is different. You are only submitting the `Inventory.db` file.
    1.  Initialize a Git repository in your project folder.
    2.  Add and commit the `Inventory.db` file.
    3.  Push it to a new GitHub repository for the week.

---
