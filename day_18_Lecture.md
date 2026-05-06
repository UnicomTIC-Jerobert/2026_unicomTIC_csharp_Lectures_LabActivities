# Week 4, Day 3: Modifying Data from C# (Create, Update, Delete)

## 📖 Lecture Notes (1 Hour)

### 1. Introduction: Beyond Reading Data
Reading data is essential, but a truly dynamic application must also be able to change its data. It needs to add new records, modify existing ones, and remove old ones. Today we complete the **CRUD** acronym: **C**reate, **R**ead, **U**pdate, **D**elete.

To do this, we'll use the SQL commands we learned on Day 1 (`INSERT`, `UPDATE`, `DELETE`) but execute them from our C# code.

### 2. `ExecuteNonQuery()`: The Command for Action
When we executed a `SELECT` query yesterday, we needed a `SqliteDataReader` to read the rows that came back. But what about `INSERT`, `UPDATE`, or `DELETE`? These commands don't return a set of rows. They simply perform an action and report back on how many rows were affected.

For these "action queries," we use a different method on the `SqliteCommand` object:
**`command.ExecuteNonQuery()`**

*   **Non Query:** It's called this because it doesn't return a "query result" in the form of data rows.
*   **Return Value:** It returns an `int` representing the **number of rows affected** by the command.
    *   For an `INSERT`, this will usually be `1`.
    *   For an `UPDATE` or `DELETE`, this could be `0`, `1`, or many, depending on your `WHERE` clause.
*   **Usage:** You call it directly—you do not need a `SqliteDataReader`.

```csharp
string sql = "DELETE FROM Products WHERE ProductID = 101;";
using (SqliteCommand command = new SqliteCommand(sql, connection))
{
    int rowsAffected = command.ExecuteNonQuery();
    Console.WriteLine($"{rowsAffected} row(s) deleted.");
}
```

### 3. The Number One Security Threat: SQL Injection
This is one of the most famous and dangerous security vulnerabilities in programming. Consider this "insecure" code for adding a product:

```csharp
// DANGEROUS CODE - DO NOT USE
string productName = "Coffee Mug"; // Let's imagine this came from a user's TextBox
string sql = "INSERT INTO Products (Name) VALUES ('" + productName + "');";
// The final SQL string becomes: "INSERT INTO Products (Name) VALUES ('Coffee Mug');"
```
This looks fine. But what if a malicious user types this into the `TextBox`?
`productName = "Fake Product'); DELETE FROM Products; --";`

Our C# code will happily build the following SQL string:
`INSERT INTO Products (Name) VALUES ('Fake Product'); DELETE FROM Products; --');`

When the database executes this, it sees **two complete, valid commands**. It will insert the fake product, and then it will **delete every single row from your products table**.

### 4. The Solution: Parameterized Queries
**Never, ever build SQL queries by concatenating user input strings.**

The correct, secure way to handle this is with **Parameterized Queries**. We use placeholders (parameters) in our SQL string, and then we provide the values for those placeholders separately. The database driver ensures that the values are treated purely as data and never as executable SQL code.

**The Safe Way:**
```csharp
// 1. Use placeholders (e.g., @name, @price) in the SQL string.
string sql = "INSERT INTO Products (Name, Price, Stock) VALUES (@name, @price, @stock);";

using (SqliteCommand command = new SqliteCommand(sql, connection))
{
    // 2. Add values for the parameters. The name MUST match the placeholder.
    // The driver handles quoting and escaping to prevent injection.
    command.Parameters.AddWithValue("@name", productName);
    command.Parameters.AddWithValue("@price", productPrice);
    command.Parameters.AddWithValue("@stock", productStock);

    // 3. Execute the command.
    command.ExecuteNonQuery();
}
```
By using parameters, you completely eliminate the risk of SQL Injection. **This is not optional; it is the only professional way to write database code.**

---
