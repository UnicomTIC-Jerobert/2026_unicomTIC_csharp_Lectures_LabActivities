Of course. Let's proceed to **Week 3, Day 3**. Today we explore another essential generic collection, the **Dictionary**, which is optimized for incredibly fast lookups using a key-value system.

Here is the complete curriculum following your established structure: 1-hour lecture, a minimum of 7 hands-on lab activities for Console and WPF, and a comprehensive 20-question quiz.

***

# Week 3, Day 3: Dictionaries (`Dictionary<TKey, TValue>`)

## 📖 Lecture Notes (1 Hour)

### 1. Introduction: The Problem with Searching a List
Imagine you have a `List<Student>` with thousands of students. If you want to find the student with `StudentID == 5839`, what do you have to do? You must loop through the entire list, checking each student one by one until you find a match. This is slow and inefficient, especially for large collections.

What if you could go directly to the student's record, just like looking up a word in a dictionary? You don't read the whole dictionary; you use the word (the **key**) to find its definition (the **value**) instantly. This is the exact purpose of the **Dictionary** collection.

### 2. What is a `Dictionary<TKey, TValue>`?
A `Dictionary<TKey, TValue>` is a collection of **key-value pairs**. It is designed for optimized, high-performance lookups.

*   **Generic (`<TKey, TValue>`):** It is generic over two types:
    *   `TKey`: The type of the key (e.g., `int` for a Student ID, `string` for a username).
    *   `TValue`: The type of the value (e.g., a `Student` object, a `string` for a password).
*   **Unique Keys:** The most important rule: **every key in a dictionary must be unique**. You cannot have two entries with the same key.
*   **Unordered:** Unlike a List, a Dictionary does not guarantee the order of its elements. It's organized for fast lookups, not for sequential access.
*   **Part of `System.Collections.Generic`:** Just like `List<T>`.

### 3. Dictionary Syntax and Common Operations
`Dictionary<int, string> studentNames = new Dictionary<int, string>();`

*   **Adding Items:**
    `studentNames.Add(101, "Alice");`
    `studentNames.Add(102, "Bob");`
    // This would crash! Key 101 already exists.
    // studentNames.Add(101, "Alicia");
*   **Accessing Values by Key (The "Indexer"):**
    `string name = studentNames[101]; // name is now "Alice"`
*   **Checking for a Key:** Trying to access a key that doesn't exist will crash the program. You should always check first.
    `if (studentNames.ContainsKey(105)) { /* access it safely */ }`
*   **Safely Getting a Value (`TryGetValue`):** A more efficient way to check and get the value in one step.
    ```csharp
    if (studentNames.TryGetValue(102, out string foundName))
    {
        // This code only runs if the key exists.
        // foundName is now "Bob".
    }
    ```
*   **Removing Items:**
    `studentNames.Remove(102); // Removes the entry with key 102.`
*   **`.Count` Property:** Gets the number of key-value pairs in the dictionary.

### 4. Iterating Over a Dictionary
Since a dictionary has both keys and values, the `foreach` loop works a bit differently. It iterates over a collection of `KeyValuePair<TKey, TValue>` objects.

```csharp
Dictionary<string, double> productPrices = new Dictionary<string, double>
{
    { "Laptop", 1200.00 },
    { "Mouse", 25.50 },
    { "Keyboard", 75.00 }
};

foreach (KeyValuePair<string, double> product in productPrices)
{
    Console.WriteLine($"Product: {product.Key}, Price: ${product.Value}");
}

// You can also iterate just the keys or just the values
foreach (string key in productPrices.Keys) { /* ... */ }
foreach (double value in productPrices.Values) { /* ... */ }
```

### 5. Use Cases: When to Choose a Dictionary
*   **Unique Identifiers:** Any time you have a collection of objects that each have a unique ID (Product ID, User ID, ISBN for a book), a dictionary is the perfect choice. `Dictionary<int, Product>`.
*   **Configuration Settings:** Mapping setting names to their values. `Dictionary<string, string>`.
*   **Counting Occurrences:** Mapping an item to its count. `Dictionary<string, int>`.
*   **Any "Lookup" Scenario:** When the primary operation is "find me the thing associated with this identifier," a dictionary will outperform a list.

---
