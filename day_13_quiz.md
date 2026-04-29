## 🎓 Daily Quiz (End of Day)

**Instructions:** Choose the best answer for each question.

1.  What is the primary strength of a `Dictionary<TKey, TValue>`?
    a) It maintains the original order of elements.
    b) It has a dynamic size.
    c) It provides very fast lookups based on a key.
    d) It can store elements of different types.

2.  What is the most important rule regarding keys in a dictionary?
    a) Keys must be strings.
    b) Keys must be unique.
    c) Keys must be integers.
    d) Keys are optional.

3.  Which line correctly creates a dictionary mapping user IDs (`int`) to usernames (`string`)?
    a) `Dictionary<int, string> users = new Dictionary<int, string>();`
    b) `Dictionary<string, int> users = new Dictionary<string, int>();`
    c) `new Dictionary<int, string>() = users;`
    d) `List<int, string> users = new List<int, string>();`

4.  How do you add a new entry to a dictionary named `ages`?
    a) `ages.Push("John", 30);`
    b) `ages.Add("John", 30);`
    c) `ages.Insert("John", 30);`
    d) `ages["John"] = 30;` (This also works for adding if the key doesn't exist).

5.  What happens if you try to access a dictionary key that does not exist using the indexer `[]`?
    a) It returns `null`.
    b) It returns `0`.
    c) It causes a run-time exception.
    d) It adds the key automatically.

6.  Which method should you use to safely check for a key's existence before accessing it?
    a) `HasKey()`
    b) `Exists()`
    c) `ContainsKey()`
    d) `IsKeyPresent()`

7.  What does the `TryGetValue()` method do?
    a) It tries to get a value and returns `null` if it fails.
    b) It returns a boolean indicating if the key was found, and sets an `out` parameter to the value if successful.
    c) It returns the value if found, otherwise it throws an exception.
    d) It gets the value or creates a new entry if the key doesn't exist.

8.  When you `foreach` over a dictionary, what is the type of the loop variable?
    a) `object`
    b) `TKey`
    c) `TValue`
    d) `KeyValuePair<TKey, TValue>`

9.  Given `Dictionary<string, int> d`, what does `d.Keys` return?
    a) A `List<string>` of all keys.
    b) An `array` of all keys.
    c) A collection of all keys.
    d) A `List<KeyValuePair<string, int>>`.

10. What is the output of this code?
    ```csharp
    var d = new Dictionary<int, string>();
    d.Add(1, "A");
    d.Add(2, "B");
    d.Remove(1);
    Console.WriteLine(d.Count);
    ```
    a) 0 b) 1 c) 2 d) An error occurs.

11. What is a "key-value pair"?
    a) A special type of array.
    b) The combination of a key and its associated value in a dictionary.
    c) Two lists that are linked together.
    d) The first and last element of a collection.

12. You would choose a `Dictionary` over a `List` when...
    a) You need to store elements in a specific order.
    b) You have a small number of items.
    c) Your primary operation is looking up items by a unique identifier.
    d) You need to frequently add and remove items from the end of the collection.

13. What is the output?
    ```csharp
    var d = new Dictionary<string, int>();
    d["a"] = 1;
    d["b"] = 2;
    d["a"] = 3;
    Console.WriteLine(d["a"]);
    ```
    a) 1 b) 2 c) 3 d) An error occurs.

14. How would you iterate through only the values in a dictionary `d`?
    a) `foreach (var val in d.Values)`
    b) `foreach (var val in d)`
    c) `for (int i=0; i < d.Count; i++)`
    d) `foreach (var val in d.TValue)`

15. What is the Big O notation for a lookup in a dictionary (on average)?
    a) O(1) - Constant time
    b) O(n) - Linear time
    c) O(log n) - Logarithmic time
    d) O(n^2) - Quadratic time

16. Which of the following can be used as a dictionary key?
    a) A `List<int>`
    b) A `string`
    c) An `object`
    d) Any type that correctly implements `GetHashCode()` and `Equals()` (like `string` and `int`).

17. If you use a custom object as a key, what must you do for the dictionary to work correctly?
    a) Nothing, it works automatically.
    b) Override the `ToString()` method.
    c) Implement the `IComparable` interface.
    d) Override the `GetHashCode()` and `Equals()` methods.

18. What does `d.Clear()` do?
    a) Deletes the dictionary object.
    b) Sets all values to `null`.
    c) Removes all key-value pairs from the dictionary.
    d) Resets the capacity to 0.

19. In WPF, a dictionary is an excellent choice for a...
    a) ListBox that needs to be sorted.
    b) Backend for a lookup UI, like a phone book or product catalog.
    c) Grid that displays rows and columns.
    d) Progress bar.

20. What is the primary limitation of a dictionary?
    a) It is slow for adding items.
    b) It uses a large amount of memory.
    c) The elements are not stored in a predictable order.
    d) It cannot store custom objects.

---
<details>
  <summary><strong>ANSWER KEY</strong></summary>
  
  1. **c)** It provides very fast lookups based on a key.
  2. **b)** Keys must be unique.
  3. **a)** `Dictionary<int, string> users = new Dictionary<int, string>();`
  4. **b)** `ages.Add("John", 30);` (and d is also correct for both adding and updating).
  5. **c)** It causes a run-time exception.
  6. **c)** `ContainsKey()`
  7. **b)** It returns a boolean indicating if the key was found, and sets an `out` parameter to the value if successful.
  8. **d)** `KeyValuePair<TKey, TValue>`
  9. **c)** A collection of all keys.
  10. **b)** 1
  11. **b)** The combination of a key and its associated value in a dictionary.
  12. **c)** Your primary operation is looking up items by a unique identifier.
  13. **c)** 3 (Using the indexer on an existing key updates its value).
  14. **a)** `foreach (var val in d.Values)`
  15. **a)** O(1) - Constant time
  16. **d)** Any type that correctly implements `GetHashCode()` and `Equals()` (like `string` and `int`).
  17. **d)** Override the `GetHashCode()` and `Equals()` methods.
  18. **c)** Removes all key-value pairs from the dictionary.
  19. **b)** Backend for a lookup UI, like a phone book or product catalog.
  20. **c)** The elements are not stored in a predictable order.
</details>
