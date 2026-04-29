## 💻 Lab Activities (6 Hours)

### **Objective**
To master writing LINQ queries to filter, project, order, and aggregate data from collections like `List<T>` and arrays, using both method syntax and lambda expressions.

### **Setup for All Activities**
Create a single Console App `Day14_LINQ_Labs`. In `Program.cs`, create a `Product` class and a static method to give you sample data. This will be the data source for all console activities.
```csharp
public class Product
{
    public int Id { get; set; }
    public string Name { get; set; }
    public string Category { get; set; }
    public double Price { get; set; }
    public int UnitsInStock { get; set; }
}

public static List<Product> GetSampleProducts()
{
    return new List<Product>
    {
        new Product { Id = 1, Name = "Laptop", Category = "Electronics", Price = 1200.50, UnitsInStock = 10 },
        new Product { Id = 2, Name = "Mouse", Category = "Electronics", Price = 25.00, UnitsInStock = 30 },
        new Product { Id = 3, Name = "Keyboard", Category = "Electronics", Price = 75.75, UnitsInStock = 20 },
        new Product { Id = 4, Name = "Novel - 'Dune'", Category = "Books", Price = 15.50, UnitsInStock = 50 },
        new Product { Id = 5, Name = "Comic Book", Category = "Books", Price = 4.25, UnitsInStock = 100 },
        new Product { Id = 6, Name = "Coffee Mug", Category = "Home", Price = 12.00, UnitsInStock = 0 },
        new Product { Id = 7, Name = "Desk Chair", Category = "Home", Price = 150.00, UnitsInStock = 5 }
    };
}
```

### **Activity 1 (~30 mins): Basic Filtering with `Where`**
*   **Concept:** Selecting a subset of data based on a condition.
*   **Task:**
    1.  In `Main`, get the list of sample products.
    2.  Write a LINQ query to find all products in the "Electronics" category.
    3.  Write another query to find all products that cost more than $100.
    4.  Write a third query to find all products that are out of stock (`UnitsInStock == 0`).
    5.  For each query, use a `foreach` loop to print the names of the resulting products.

### **Activity 2 (~30 mins): Transformation with `Select`**
*   **Concept:** Projecting data into a new form.
*   **Task:**
    1.  Write a LINQ query to get a collection of just the **names** of all products (`List<string>`).
    2.  Write a query to get a collection of just the **prices** (`List<double>`).
    3.  Write a query to create a new collection of strings, where each string is formatted as `"{Name} - ${Price}"`.
    4.  Print the results of each query.

### **Activity 3 (~35 mins): Ordering with `OrderBy`**
*   **Concept:** Sorting collections based on properties.
*   **Task:**
    1.  Write a LINQ query to get all products ordered by `Name` alphabetically (A-Z).
    2.  Write a query to get all products ordered by `Price` from cheapest to most expensive.
    3.  Write a query to get all products ordered by `UnitsInStock` from most in-stock to least (`OrderByDescending`).
    4.  Print the names and the relevant property for each sorted list.

### **Activity 4 (~35 mins): Chaining LINQ Methods**
*   **Concept:** Combining multiple LINQ operations to form a complex query.
*   **Task:**
    1.  Write a **single** chained LINQ query to find all products in the "Electronics" category, ordered by price from high to low.
    2.  Write a single query to get the **names** of all products from the "Books" category that have more than 40 units in stock.
    3.  Print the results of each query.

### **Activity 5 (~35 mins): Aggregation Methods**
*   **Concept:** Calculating single values from a collection.
*   **Task:**
    1.  Calculate the total number of products in the inventory using `.Count()`.
    2.  Calculate the total number of units in stock for all products combined using `.Sum()`.
    3.  Find the price of the most expensive product using `.Max()`.
    4.  Find the average price of all products in the "Home" category.
    5.  Print each result with a descriptive label.

### **Activity 6 (~35 mins): Element Operators**
*   **Concept:** Selecting a single specific element from a collection.
*   **Task:**
    1.  Find the very first product in the list using `.First()`.
    2.  Find the product with `Id == 5` using `.First(p => p.Id == 5)`.
    3.  Try to find the product with `Id == 99` using `.First()`. Wrap this in a `try-catch` block to handle the exception.
    4.  Now, find the product with `Id == 99` using `.FirstOrDefault()`. Check if the result is `null` before trying to print its name.

### **Activity 7 (~45 mins): WPF Search/Filter UI**
*   **Concept:** Using LINQ to power a dynamic user interface.
*   **WPF:** Create `Day14_Activity7_WPF_Filter`.
    1.  Design a UI with:
        *   A `TextBox` named `SearchTextBox`.
        *   A "Search" `Button`.
        *   A `ListBox` named `ResultsListBox`.
    2.  In the code-behind, get the sample product list and store it in a member variable. Initially, load all products into the `ListBox`. (Override `ToString()` in your `Product` class).
    3.  Implement the "Search" button's `Click` event. It should:
        *   Get the search term from the `SearchTextBox`.
        *   Use a LINQ `.Where()` query on your master list of products to find all products whose `Name` (converted to lowercase) `Contains` the search term (also converted to lowercase).
        *   Clear the `ListBox` and display only the results of the query.

### **Activity 8 (~15 mins): Git Submission**
*   **Task:** Stage, commit, and push your new projects to GitHub with the message: `"Day 14 Labs: LINQ and Lambda Expressions"`.

---
