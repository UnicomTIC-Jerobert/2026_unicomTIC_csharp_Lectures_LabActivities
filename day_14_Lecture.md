# Week 3, Day 4: LINQ (Language-Integrated Query)

## 📖 Lecture Notes (1 Hour)

### 1. Introduction: The "Old Way" of Querying Data
Imagine you have a `List<Product>` and you need to find all products that are more expensive than $50, in stock, and sorted by name. How would you do it?

The "old way" would look something like this:
1.  Create an empty `List<Product>` called `results`.
2.  Write a `foreach` loop to iterate through the original list.
3.  Inside the loop, write an `if` statement to check `product.Price > 50 && product.InStock == true`.
4.  If the condition is true, add the product to the `results` list.
5.  After the loop, call a method to sort the `results` list by name.

This works, but it's a lot of code (we call this "boilerplate" code). It's verbose and can be hard to read.

### 2. LINQ: A Better Way to Query
**LINQ (Language-Integrated Query)** is a powerful set of features built directly into the C# language that allows you to write declarative queries against data collections. Instead of telling the computer *how* to get the data (the loops and ifs), you just describe *what* data you want.

Here's that same problem solved with LINQ:
```csharp
var results = inventory
    .Where(product => product.Price > 50 && product.InStock == true)
    .OrderBy(product => product.Name)
    .ToList();
```
This code is more concise, more readable, and clearly expresses the *intent* of the query.

### 3. Core Concepts: Lambda Expressions and Extension Methods
LINQ is built on two key C# features:
*   **Extension Methods:** These are special static methods that allow you to "add" new methods to existing types without modifying them. LINQ methods like `Where()`, `OrderBy()`, and `Select()` are extension methods that appear on collection types like `List<T>`.
*   **Lambda Expressions (`=>`):** A lambda expression is a short, anonymous function. It's a shorthand way of writing a simple method that you'll only use once.
    *   `product => product.Price > 50` can be read as: "Given a product, return true if its price is greater than 50."
    *   The `=>` is called the "lambda operator."
    *   The variable on the left (`product`) is the input parameter.
    *   The expression on the right is the logic to be executed.

### 4. The Most Common LINQ Methods
These are the building blocks you will use in almost every query.

*   **Filtering (`Where`):**
    *   Returns a new collection containing only the elements that satisfy a condition.
    *   The lambda expression must return a `bool`.
    *   `numbers.Where(n => n % 2 == 0); // Get all even numbers`
*   **Projection/Transformation (`Select`):**
    *   Transforms each element of a collection into something new.
    *   `products.Select(p => p.Name); // Get a collection of just the names (string)`
    *   `numbers.Select(n => n * 2); // Get a collection where each number is doubled`
*   **Ordering (`OrderBy` / `OrderByDescending`):**
    *   Sorts the elements of a collection.
    *   `products.OrderBy(p => p.Price); // Sort products from cheapest to most expensive`
    *   `products.OrderByDescending(p => p.Name); // Sort names from Z to A`
*   **Aggregation (`Sum`, `Average`, `Count`, `Min`, `Max`):**
    *   Performs a calculation on a collection and returns a single value.
    *   `prices.Sum();`
    *   `products.Count(p => p.IsInStock); // Count how many products are in stock`
*   **Element Operators (`First`, `FirstOrDefault`, `Single`, `SingleOrDefault`):**
    *   Gets a single element from a collection.
    *   `products.First(p => p.Id == 101); // Get the first product with Id 101. Crashes if not found.`
    *   `products.FirstOrDefault(p => p.Id == 101); // Same, but returns null if not found (safer).`

### 5. Chaining Methods and Deferred Execution
*   **Chaining:** The real power of LINQ is "chaining" methods together. The output of one method becomes the input for the next. The order matters!
    `inventory.Where(...).OrderBy(...).Select(...);`
*   **Deferred Execution:** LINQ queries do **not** run when you define them. They only execute when you actually try to access the results (e.g., by using a `foreach` loop, or by calling `.ToList()`, `.ToArray()`, or an aggregation method like `.Count()`).

---
