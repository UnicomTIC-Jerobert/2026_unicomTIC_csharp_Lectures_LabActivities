Of course. Let's proceed to the next step: **Week 3, Day 2**. Today, we address the primary limitation of arrays by introducing the most commonly used collection in C#: the **Generic List**.

This curriculum follows your established structure, with 1 hour of lecture, a minimum of 7 hands-on lab activities covering Console and WPF, and a comprehensive 20-question quiz.

***

# Week 3, Day 2: Generic List (`List<T>`)

## 📖 Lecture Notes (1 Hour)

### 1. Introduction: The Problem with Arrays
Yesterday we mastered arrays. They are fast and efficient, but they have one major drawback: they are **fixed-size**. If you create an array for 5 friends and you make a 6th friend, you can't just add them. You have to create a brand new, larger array and copy all the old elements over. This is highly inefficient.

What we need is a "smart" array that can **grow and shrink automatically** as we add or remove items. This is exactly what the **Generic List**, or `List<T>`, provides.

### 2. What is a `List<T>`?
A `List<T>` is the most popular collection type in C#. It represents a strongly-typed list of objects that can be accessed by index and provides methods to search, sort, and manipulate the list.

*   **Generic (`<T>`):** The `<T>` is a placeholder for a specific type. This is what makes it "strongly-typed". You must declare what type of items the list will hold. This prevents you from accidentally adding a `Book` object to a `List<int>`.
    *   `List<int>` can only hold integers.
    *   `List<string>` can only hold strings.
    *   `List<Student>` can only hold `Student` objects.
*   **Dynamic Size:** Its most important feature. It automatically handles resizing behind the scenes.
*   **Part of `System.Collections.Generic`:** To use it, you usually need to add `using System.Collections.Generic;` at the top of your file.

### 3. `List<T>` vs. `Array`: Key Differences
| Feature | `int[]` (Array) | `List<int>` (List) |
| :--- | :--- | :--- |
| **Size** | Fixed | Dynamic (grows and shrinks) |
| **Creation** | `new int[10];` (must specify size) | `new List<int>();` (starts empty) |
| **Adding Items** | `myArray[i] = value;` | `myList.Add(value);` |
| **Getting Size** | `.Length` property | `.Count` property |
| **Use Case** | When size is known and won't change. | The default choice for most situations. |

### 4. Common `List<T>` Methods and Properties
A `List<T>` is powerful because of its built-in methods.

*   **`myList.Add(item);`**: Adds an item to the **end** of the list.
*   **`myList.Remove(item);`**: Searches for the specified item and removes the **first** occurrence of it.
*   **`myList.RemoveAt(index);`**: Removes the item at the specified **index**.
*   **`myList.Insert(index, item);`**: Inserts an item at a specific index, shifting everything else down.
*   **`myList.Clear();`**: Removes all items from the list.
*   **`myList.Contains(item);`**: Returns `true` if the list contains the specified item, otherwise `false`.
*   **`myList.Count`**: A property (like `Length` for arrays) that gets the number of items currently in the list.

### 5. Iterating Over a List
Iteration works exactly the same way as it does for arrays.

*   **`for` Loop (when you need the index):**
    ```csharp
    List<string> names = new List<string> { "Alice", "Bob" };
    for (int i = 0; i < names.Count; i++) // Use .Count!
    {
        Console.WriteLine(names[i]);
    }
    ```
*   **`foreach` Loop (simpler, more common):**
    ```csharp
    foreach (string name in names)
    {
        Console.WriteLine(name);
    }
    ```

### 6. Lists of Objects
The true power of a `List<T>` shines when you use it to manage a collection of your custom objects. This is the foundation of almost every modern application.

```csharp
List<Product> inventory = new List<Product>();

inventory.Add(new Product { Name = "Laptop", Price = 1200.00 });
inventory.Add(new Product { Name = "Mouse", Price = 25.00 });

foreach (Product p in inventory)
{
    Console.WriteLine(p.Name);
}
```

---
