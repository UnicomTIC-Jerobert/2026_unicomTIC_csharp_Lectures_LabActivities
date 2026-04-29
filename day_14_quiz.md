## 🎓 Daily Quiz (End of Day)

**Instructions:** Choose the best answer for each question.

1.  What does LINQ stand for?
    a) Language Integration Query
    b) List Inquiry
    c) Language-Integrated Query
    d) Linked-In Query

2.  What is the primary purpose of the LINQ `Where` method?
    a) To sort a collection.
    b) To transform each element.
    c) To filter a collection based on a condition.
    d) To find a single element.

3.  What is the `=>` symbol called in C#?
    a) Arrow operator
    b) Lambda operator
    c) Goes-to operator
    d) Selection operator

4.  Which LINQ method would you use to convert a `List<Product>` into a `List<string>` containing only the product names?
    a) `Where` b) `Select` c) `Convert` d) `Transform`

5.  What is "Deferred Execution" in LINQ?
    a) The query runs on a background thread.
    b) The query execution is delayed until the results are actually requested.
    c) The query must be explicitly started with a `.Run()` method.
    d) The query runs very slowly.

6.  Which method is safer to use if you are not sure an element exists?
    a) `First()`
    b) `Single()`
    c) `FirstOrDefault()`
    d) `ElementAt(0)`

7.  What does the `OrderByDescending()` method do?
    a) Sorts in alphabetical order (A-Z).
    b) Sorts in reverse alphabetical order (Z-A) or high-to-low for numbers.
    c) Removes elements in descending order.
    d) Reverses the order of the list.

8.  The expression `n => n > 10` is an example of a...
    a) Extension Method
    b) LINQ Query
    c) Lambda Expression
    d) Anonymous Object

9.  What is the result of this query? `new List<int> { 1, 2, 3, 4 }.Sum();`
    a) 4 b) 10 c) An error d) `1234`

10. Which of the following is NOT an aggregation method?
    a) `Sum` b) `Max` c) `Count` d) `Where`

11. What is the output?
    ```csharp
    var nums = new List<int> { 10, 20, 30 };
    var result = nums.Where(n => n > 15);
    Console.WriteLine(result.Count());
    ```
    a) 1 b) 2 c) 3 d) 0

12. To chain LINQ methods, you...
    a) Use the `&` symbol between them.
    b) Call them one after another, separated by dots.
    c) Pass one method as a parameter to the next.
    d) You cannot chain LINQ methods.

13. What data type does the lambda expression for the `Where` method need to return?
    a) `int` b) `string` c) `bool` d) `object`

14. The `.ToList()` method at the end of a LINQ query...
    a) Is required for all queries.
    b) Converts the query result into a new `List<T>`, forcing immediate execution.
    c) Sorts the list.
    d) Is only a comment.

15. What does this query do? `students.OrderBy(s => s.LastName).ThenBy(s => s.FirstName)`
    a) It's invalid syntax. b) Sorts by first name, then by last name. c) Sorts by last name, and for students with the same last name, it then sorts them by first name. d) Sorts by last name only.

16. LINQ can be used to query which of the following?
    a) Arrays b) `List<T>` c) Dictionaries d) All of the above.

17. What is the output of this query?
    ```csharp
    var words = new List<string> { "apple", "banana", "cherry" };
    var result = words.Select(w => w.Length);
    // foreach loop to print result
    ```
    a) `apple, banana, cherry` b) `a, b, c` c) `5, 6, 6` d) An error.

18. `Count()` vs `Count(lambda)`: What is the difference?
    a) There is no difference.
    b) `Count()` gets the total number of items; `Count(lambda)` gets the number of items that match a condition.
    c) `Count()` is faster.
    d) `Count(lambda)` is obsolete.

19. In WPF, LINQ is extremely useful for...
    a) Defining animations.
    b) Creating UI controls.
    c) Filtering and sorting data that will be displayed in a `ListBox` or `DataGrid`.
    d) Handling mouse clicks.

20. What is the value of `firstEven`?
    ```csharp
    var nums = new List<int> { 1, 3, 4, 5, 6 };
    int firstEven = nums.First(n => n % 2 == 0);
    ```
    a) 1 b) 3 c) 4 d) 6

---
<details>
  <summary><strong>ANSWER KEY</strong></summary>
  
  1. **c)** Language-Integrated Query
  2. **c)** To filter a collection based on a condition.
  3. **b)** Lambda operator
  4. **b)** `Select`
  5. **b)** The query execution is delayed until the results are actually requested.
  6. **c)** `FirstOrDefault()`
  7. **b)** Sorts in reverse alphabetical order (Z-A) or high-to-low for numbers.
  8. **c)** Lambda Expression
  9. **b)** 10
  10. **d)** `Where`
  11. **b)** 2
  12. **b)** Call them one after another, separated by dots.
  13. **c)** `bool`
  14. **b)** Converts the query result into a new `List<T>`, forcing immediate execution.
  15. **c)** Sorts by last name, and for students with the same last name, it then sorts them by first name.
  16. **d)** All of the above.
  17. **c)** `5, 6, 6`
  18. **b)** `Count()` gets the total number of items; `Count(lambda)` gets the number of items that match a condition.
  19. **c)** Filtering and sorting data that will be displayed in a `ListBox` or `DataGrid`.
  20. **c)** 4 (`First` stops as soon as it finds a match).
</details>
