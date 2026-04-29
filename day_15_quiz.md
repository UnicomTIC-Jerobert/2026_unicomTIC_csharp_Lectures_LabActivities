## 🎓 Weekly Review Quiz (End of Day)

**Instructions:** This quiz covers all topics from Week 3. Choose the best answer.

1.  Which collection has a fixed size?
    a) `List<T>` b) `Dictionary<TKey, TValue>` c) `Array` d) `ArrayList`
2.  Which collection is best for fast lookups using a unique identifier?
    a) `List<T>` b) `Dictionary<TKey, TValue>` c) `Array` d) `Queue<T>`
3.  What property gives you the number of items in a `List<T>`?
    a) `.Length` b) `.Size` c) `.Count` d) `.Capacity`
4.  What does the LINQ `Where` method do?
    a) Sorts a collection. b) Filters a collection based on a condition. c) Transforms each element. d) Counts the elements.
5.  What does the LINQ `Select` method do?
    a) Finds a single element. b) Filters a collection. c) Transforms each element into a new form. d) Sorts the collection.
6.  The `=>` syntax is used for what C# feature?
    a) Inheritance b) Interface implementation c) Lambda Expressions d) Constructors
7.  What is the index of the first element in an array or list?
    a) 1 b) `First` c) -1 d) 0
8.  Which method adds an item to the end of a `List<T>`?
    a) `Add()` b) `Insert()` c) `Push()` d) `Append()`
9.  What is a key-value pair?
    a) The first and last items in a list. b) The data structure used by Dictionaries. c) An array with two elements. d) A special type of class.
10. What is the output of this LINQ query? `new List<int> { 1, 2, 3, 4, 5 }.Count(n => n % 2 == 0);`
    a) 5 b) 3 c) 2 d) An error.
11. Trying to access a dictionary key that doesn't exist with the `[]` indexer will cause...
    a) A `null` return value. b) An `IndexOutOfRangeException`. c) A `KeyNotFoundException`. d) The key to be created automatically.
12. What does `.FirstOrDefault()` do if no matching element is found?
    a) Throws an exception. b) Returns the first item in the list. c) Returns the default value for the type (e.g., `null` for objects). d) Returns `-1`.
13. Which loop is generally considered more readable for simple iteration where the index is not needed?
    a) `for` b) `while` c) `do-while` d) `foreach`
14. What does the LINQ `.Sum()` method do?
    a) Adds two numbers. b) Concatenates strings. c) Calculates the total of a numeric collection. d) Summarizes a text file.
15. A "Repository" class is a design pattern used to...
    a) Style UI elements. b) Encapsulate data access and management logic. c) Define core business objects. d) Handle user input.
16. To get only the unique items from a list, you would chain which LINQ method?
    a) `.Unique()` b) `.Distinct()` c) `.Filter()` d) `.Single()`
17. What is the main difference between `Remove(item)` and `RemoveAt(index)` on a `List<T>`?
    a) `Remove` is faster. b) `Remove` works on the value, `RemoveAt` works on the position. c) `RemoveAt` can remove multiple items. d) There is no difference.
18. What is the best collection for storing a fixed set of constants that will never change?
    a) `List<T>` b) `Dictionary<TKey, TValue>` c) `Array`
19. `OrderByDescending()` sorts a collection of numbers from...
    a) Low to high. b) High to low. c) The middle out. d) Randomly.
20. The primary purpose of using LINQ is to...
    a) Make code run faster. b) Write declarative, readable, and powerful queries against data collections. c) Reduce memory usage. d) Replace the need for `if` statements.

---
<details>
  <summary><strong>ANSWER KEY</strong></summary>
  
  1. **c)** `Array`
  2. **b)** `Dictionary<TKey, TValue>`
  3. **c)** `.Count`
  4. **b)** Filters a collection based on a condition.
  5. **c)** Transforms each element into a new form.
  6. **c)** Lambda Expressions
  7. **d)** 0
  8. **a)** `Add()`
  9. **b)** The data structure used by Dictionaries.
  10. **c)** 2 (The even numbers are 2 and 4).
  11. **c)** A `KeyNotFoundException`.
  12. **c)** Returns the default value for the type (e.g., `null` for objects).
  13. **d)** `foreach`
  14. **c)** Calculates the total of a numeric collection.
  15. **b)** Encapsulate data access and management logic.
  16. **b)** `.Distinct()`
  17. **b)** `Remove` works on the value, `RemoveAt` works on the position.
  18. **c)** `Array`
  19. **b)** High to low.
  20. **b)** Write declarative, readable, and powerful queries against data collections.
</details>
