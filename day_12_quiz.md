## 🎓 Daily Quiz (End of Day)

**Instructions:** Choose the best answer for each question.

1.  What is the primary advantage of a `List<T>` over an array `T[]`?
    a) `List<T>` is faster for accessing elements.
    b) `List<T>` has a dynamic size; it can grow and shrink.
    c) `List<T>` can hold elements of different types.
    d) `List<T>` uses less memory.

2.  What does the `<T>` in `List<T>` stand for?
    a) The initial size of the list.
    b) A placeholder for a specific, generic type.
    c) The total capacity of the list.
    d) A keyword meaning "Text".

3.  Which line correctly creates an empty list that can hold `Book` objects?
    a) `List<Book> books = new List();`
    b) `Book<List> books = new Book<List>();`
    c) `List<Book> books = new List<Book>();`
    d) `List books = new List<Book>();`

4.  Which method adds a new element to the end of a list?
    a) `Insert()` b) `Push()` c) `Add()` d) `Append()`

5.  What property do you use to find out how many items are currently in a `List<T>`?
    a) `.Length` b) `.Size` c) `.Capacity` d) `.Count`

6.  Which method removes the element at a specific index?
    a) `Remove()` b) `Delete()` c) `RemoveAt()` d) `RemoveIndex()`

7.  What does the `myList.Contains("apple")` method return?
    a) The index of "apple".
    b) The item "apple".
    c) A boolean (`true` or `false`).
    d) The number of times "apple" appears.

8.  What is the output of this code?
    ```csharp
    var numbers = new List<int> { 1, 2, 3 };
    numbers.Remove(2);
    foreach (int n in numbers) { Console.Write(n); }
    ```
    a) `12` b) `13` c) `23` d) `123`

9.  Which namespace is required to use `List<T>`?
    a) `System.Collections`
    b) `System.Collections.Generic`
    c) `System.List`
    d) `System.Data`

10. What is the value of `names.Count` after this code runs?
    ```csharp
    var names = new List<string>();
    names.Add("A");
    names.Add("B");
    names.Clear();
    ```
    a) 0 b) 1 c) 2 d) An error occurs.

11. To add an element at the very beginning of a list, you would use:
    a) `myList.Add(0, item);`
    b) `myList.Insert(0, item);`
    c) `myList.Prepend(item);`
    d) `myList[0] = item;`

12. What is the key difference between `Remove(item)` and `RemoveAt(index)`?
    a) `Remove` works with values, `RemoveAt` works with positions (indices).
    b) `Remove` is faster than `RemoveAt`.
    c) `RemoveAt` can remove multiple items, `Remove` only one.
    d) There is no difference.

13. The `foreach` loop is generally a good choice for iterating a list when...
    a) You need to remove items from the list during iteration.
    b) You just need to read each item and don't need the index.
    c) You need to iterate backwards through the list.
    d) All of the above.

14. What is the capacity of a `List<T>`?
    a) The number of items currently in the list.
    b) The size of the underlying array before it needs to be resized.
    c) The maximum number of items the list can ever hold.
    d) The same as `.Count`.

15. What is the output of this code?
    ```csharp
    var letters = new List<string> { "a", "c", "d" };
    letters.Insert(1, "b");
    Console.WriteLine(letters[2]);
    ```
    a) `b` b) `c` c) `d` d) An error occurs.

16. Why is `List<string>` preferred over the older `ArrayList`?
    a) It is faster.
    b) It is "type-safe", preventing you from adding the wrong type of data.
    c) It uses less memory.
    d) `ArrayList` is not a real class.

17. To use a `List<T>` of custom objects in a WPF `ListBox`, it's a good practice to...
    a) Override the `ToString()` method in your custom class.
    b) Make all properties of your class `static`.
    c) Ensure your class inherits from `List`.
    d) Convert each object to a string before adding it.

18. If you remove an item from the middle of a `List<T>`, what happens to the indices of the elements after it?
    a) They stay the same.
    b) They all decrease by one.
    c) The list becomes invalid.
    d) They become null.

19. `List<T>` is a class that implements which interface?
    a) `IEnumerable<T>`
    b) `ICollection<T>`
    c) `IList<T>`
    d) All of the above.

20. When should you choose an array over a `List<T>`?
    a) When you need to frequently add or remove items.
    b) When performance is absolutely critical and the collection size will never, ever change.
    c) When you need to store items of different types.
    d) Almost never; `List<T>` is the modern default.

---
<details>
  <summary><strong>ANSWER KEY</strong></summary>
  
  1. **b)** `List<T>` has a dynamic size; it can grow and shrink.
  2. **b)** A placeholder for a specific, generic type.
  3. **c)** `List<Book> books = new List<Book>();`
  4. **c)** `Add()`
  5. **d)** `.Count`
  6. **c)** `RemoveAt()`
  7. **c)** A boolean (`true` or `false`).
  8. **b)** `13` (`Remove(2)` removes the *value* 2, not the item at index 2).
  9. **b)** `System.Collections.Generic`
  10. **a)** 0
  11. **b)** `myList.Insert(0, item);`
  12. **a)** `Remove` works with values, `RemoveAt` works with positions (indices).
  13. **b)** You just need to read each item and don't need the index.
  14. **b)** The size of the underlying array before it needs to be resized.
  15. **b)** `c` (After inserting "b" at index 1, "c" is shifted to index 2).
  16. **b)** It is "type-safe", preventing you from adding the wrong type of data.
  17. **a)** Override the `ToString()` method in your custom class.
  18. **b)** They all decrease by one.
  19. **d)** All of the above.
  20. **b)** When performance is absolutely critical and the collection size will never, ever change.
</details>
