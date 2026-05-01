Of course. Let's proceed to **Week 4, Day 2**.

Today, we bridge the gap between the two worlds we've explored: C# and SQL. Students will learn how to make their C# applications communicate with the SQLite database they created yesterday. The focus is specifically on **reading and retrieving data**, which is the most common database operation.

Here is the complete curriculum following your established structure.

***

# Week 4, Day 2: Connecting C# to SQLite (Reading Data)

## 📖 Lecture Notes (1 Hour)

### 1. Introduction: From Manual Queries to Programmatic Access
Yesterday, we acted as a database administrator, manually typing SQL queries into a tool to see the results. Today, we become developers. Our goal is to make our C# application do that work for us. The application itself will connect to the database, send a query, receive the results, and use that data to create objects.

### 2. ADO.NET: The Foundation of Data Access
**ADO.NET** is the core set of libraries within the .NET Framework for communicating with data sources, including relational databases. It provides a common set of classes and tools, regardless of which specific database (SQLite, SQL Server, etc.) you're using.

To work with SQLite, we need a specific **data provider**. This is a small library that knows how to translate ADO.NET commands into instructions that SQLite understands. For modern .NET, this is the `Microsoft.Data.Sqlite` package.

### 3. The Core ADO.NET Objects for Reading Data
There are three essential objects you must understand to read data from a database.

**1. `SqliteConnection`:**
*   **Purpose:** Represents the actual connection link between your application and the database file.
*   **Key Information:** It needs a **Connection String**, which is just a string that tells it where to find the database file. For SQLite, it's very simple: `Data Source=YourDatabaseFileName.db`.
*   **Lifecycle:** You must explicitly `.Open()` the connection before use and `.Close()` it when you are finished. Forgetting to close connections is a common source of bugs and resource leaks.

**2. `SqliteCommand`:**
*   **Purpose:** Represents the SQL query or command you want to execute.
*   **Key Information:** It holds the SQL text (e.g., `"SELECT * FROM Products"`) and a reference to the `SqliteConnection` object it will run on.
*   **Execution:** You call methods on the command object to actually run the query.

**3. `SqliteDataReader`:**
*   **Purpose:** Provides a way to read the results of a `SELECT` query. It is a **forward-only, read-only** stream of data from the database.
*   **Analogy:** Think of it like a tape reader. It starts before the first record and you can only move forward, one record at a time.
*   **Lifecycle:** You use a `while` loop with the `.Read()` method. `reader.Read()` does two things: it tries to advance to the next row, and it returns `true` if it was successful, or `false` if there are no more rows.

### 4. The Standard Workflow for Reading Data
This sequence is fundamental and you will use it constantly.

```csharp
// 1. Define the connection string.
string connectionString = "Data Source=Inventory.db";

// 2. Create the Connection and Command objects.
// 'using' statements are CRITICAL - they automatically close the connection for you!
using (SqliteConnection connection = new SqliteConnection(connectionString))
{
    // 3. Open the connection.
    connection.Open();

    // 4. Create the command.
    string sql = "SELECT ProductID, Name, Price FROM Products";
    using (SqliteCommand command = new SqliteCommand(sql, connection))
    {
        // 5. Execute the command and get a DataReader.
        using (SqliteDataReader reader = command.ExecuteReader())
        {
            // 6. Loop through the results.
            while (reader.Read())
            {
                // 7. Get data from the current row by column name or index.
                int id = reader.GetInt32(0); // By column index (0-based)
                string name = reader.GetString(1);
                double price = reader.GetDouble(reader.GetOrdinal("Price")); // By column name (safer)

                Console.WriteLine($"ID: {id}, Name: {name}, Price: ${price}");
            }
        } // The reader is automatically closed here.
    }
} // The connection is automatically closed here.
```
**The `using` statement is essential.** It guarantees that `.Dispose()` (which calls `.Close()`) is called on the object, even if an error occurs inside the block. Always wrap your connection, command, and reader objects in `using` blocks.

---
