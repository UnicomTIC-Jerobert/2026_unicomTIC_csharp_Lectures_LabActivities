# Week 3, Day 1: Arrays

## 📖 Lecture Notes (1 Hour)

### 1. Introduction: The Need for Collections
So far, we've stored single pieces of data in variables (`int score = 100;`) and grouped related data into objects (`Book myBook = new Book();`). But what if we need to manage a list of 50 scores, or an inventory of 100 books? Declaring 100 different variables (`book1`, `book2`, etc.) is unmanageable.

We need a way to store multiple values of the *same type* in a single variable. This is where collections come in, and the most basic collection is the **Array**.

### 2. What is an Array?
An array is a data structure that holds a **fixed-size** sequence of elements of the **same type**.

Think of it like a numbered parking garage, an egg carton, or a set of mailboxes.
*   **Fixed-Size:** When you build the parking garage with 10 spots, you cannot easily add an 11th spot. You decide the size when you create it.
*   **Same Type:** A garage for cars can only hold cars, not boats or airplanes. An `int` array can only hold `int`s.
*   **Contiguous Memory:** The elements are stored together in memory, one after the other, which makes accessing them very fast.

### 3. Array Syntax: Declaration, Instantiation, and Initialization

**1. Declaration:** Tell the compiler you want a variable that holds an array of a certain type.
`int[] scores;`
`string[] names;`

**2. Instantiation:** Actually create the array in memory with a specific size, using the `new` keyword.
`scores = new int[5]; // Creates an array that can hold 5 integers.`

**3. Declaration and Instantiation Combined (Most Common):**
`int[] scores = new int[5];`

**4. Initializer Syntax (A Convenient Shortcut):** You can declare, instantiate, and populate the array all in one go if you know the values beforehand.
`string[] daysOfWeek = { "Monday", "Tuesday", "Wednesday", "Thursday", "Friday", "Saturday", "Sunday" };`
C# automatically figures out the size is 7.

### 4. Accessing Elements: Zero-Based Indexing
This is one of the most important concepts in programming. Array elements are accessed by their **index**, which is their numerical position. C# arrays are **zero-indexed**.

*   The **first** element is at index `0`.
*   The **second** element is at index `1`.
*   ...and so on.
*   The **last** element is at index `Length - 1`.

```csharp
int[] scores = new int[3]; // Indices will be 0, 1, 2

// Assigning values using the index
scores[0] = 95;
scores[1] = 87;
scores[2] = 91;

// Reading a value using the index
Console.WriteLine($"The second score is: {scores[1]}"); // Output: The second score is: 87

// Trying to access an index that doesn't exist will crash your program!
// scores[3] = 100; // This throws an IndexOutOfRangeException
```

### 5. Iterating Over Arrays
The most common task with an array is to process every element in it.

*   **The `for` Loop (Best when you need the index):**
    The `Length` property of an array gives you its total size.
    ```csharp
    string[] names = { "Alice", "Bob", "Charlie" };
    for (int i = 0; i < names.Length; i++)
    {
        Console.WriteLine($"Name at index {i} is {names[i]}");
    }
    ```
*   **The `foreach` Loop (Best for simple, read-only iteration):**
    This is a cleaner, more readable way to loop when you don't need the index.
    ```csharp
    foreach (string name in names)
    {
        Console.WriteLine($"Hello, {name}");
    }
    ```

### 6. Arrays in Console vs. WPF
*   **Console:** Arrays are fundamental for processing collections of data, performing mathematical calculations on lists of numbers, storing user inputs, etc.
*   **WPF:** Arrays are excellent for holding a fixed set of data to populate UI elements like a `ComboBox` or a `ListBox`. You can also use an array of objects to hold the data that your UI will display.

---
