Of course. Let's proceed to **Week 4, Day 5**. This is the final day of the week and serves as the capstone mini-project, integrating everything learned about databases and the Repository Pattern into a single, polished WPF application.

This curriculum follows the established structure: a 1-hour review and architectural overview, a guided step-by-step mini-project, and a comprehensive weekly review quiz with 20 questions.

***

# Week 4, Day 5: WPF Database Mini-Project

## 📖 Lecture Notes (1 Hour)

### 1. Weekly Review: The Journey to Persistent Data
This week, we took one of the biggest steps in becoming application developers. We moved from temporary, in-memory data to permanent, persistent data. Let's recap the path we took:
*   **Day 1: SQL Fundamentals:** We learned the language of databases (`CREATE`, `SELECT`, `INSERT`, `UPDATE`, `DELETE`) and how to structure data in tables using a visual tool. We focused purely on the database itself.
*   **Day 2: Reading Data with C#:** We bridged the gap between our application and the database using ADO.NET. We learned about `SqliteConnection`, `SqliteCommand`, and the forward-only `SqliteDataReader` to bring data from the database into our C# objects.
*   **Day 3: Modifying Data from C#:** We learned to execute action queries (`INSERT`, `UPDATE`, `DELETE`) with `ExecuteNonQuery()`. Most importantly, we learned about the critical security risk of **SQL Injection** and how to prevent it completely using **Parameterized Queries**.
*   **Day 4: The Repository Pattern:** We took our raw data access code and refactored it into a clean, professional structure. The Repository Pattern encapsulates all database logic, decoupling our UI from the data layer and making our application more maintainable, testable, and organized.

### 2. The Full Application Architecture
Today, we assemble the complete picture. We will build a WPF application that demonstrates a clean, three-tier architecture.

*   **Tier 1: The Presentation Layer (The UI)**
    *   **What it is:** Our WPF Window (`MainWindow.xaml` and `MainWindow.xaml.cs`).
    *   **Its Job:** To display data to the user and to capture user input and events (button clicks, text entry).
    *   **Its Rule:** It should contain **NO** business logic or data access code. It should be as "dumb" as possible. It only knows how to talk to the next layer down.

*   **Tier 2: The Business Logic / Service Layer (The Repository)**
    *   **What it is:** Our `ProductRepository.cs` class.
    *   **Its Job:** To act as the mediator. The UI tells the repository *what* it wants ("get all products," "add this new product"). The repository contains the logic to fulfill these requests.
    *   **Its Rule:** It knows about our business objects (the `Product` class) and how to manage them. It does **NOT** know about specific UI elements like `TextBox` or `DataGrid`. It communicates with the data layer.

*   **Tier 3: The Data Access Layer (The Database)**
    *   **What it is:** The `Inventory.db` file and the ADO.NET code inside the repository.
    *   **Its Job:** To handle the low-level tasks of connecting to the database, executing SQL commands, and reading results.
    *   **Its Rule:** Its implementation details are completely hidden from the UI by the repository.

### 3. Today's Project: Inventory Management System
We will build upon the WPF project from yesterday, polishing it into a complete and functional Inventory Management System. The focus will be on ensuring a smooth user experience and a clean separation of concerns in the code.

**Key Features:**
1.  A `DataGrid` to display the current inventory from the database.
2.  A form to add new products to the inventory.
3.  The ability to select a product from the `DataGrid` to populate an "Edit" form.
4.  The ability to save changes to an existing product.
5.  The ability to delete a selected product.
6.  A "Refresh" button to ensure the UI is always in sync with the database.

This project will force students to think about the flow of data: from the database, through the repository, into C# objects, and finally displayed on the screen—and then back again.

---
