## 🎓 Daily Quiz (End of Day)

**Instructions:** Choose the best answer for each question.

1.  What is the main characteristic of an array's size?
    a) It is dynamic and can grow.
    b) It is fixed at the time of creation.
    c) It is determined by the number of elements currently stored.
    d) It is always 10.

2.  Which of the following correctly declares and instantiates an array of 10 integers?
    a) `int[] numbers = new int(10);`
    b) `int numbers[] = new int[10];`
    c) `int[] numbers = new int[10];`
    d) `int[10] numbers = new int[];`

3.  Arrays in C# are...
    a) 1-indexed
    b) Zero-indexed
    c) Not indexed
    d) Key-value pairs

4.  What is the index of the last element in `string[] names = new string[7];`?
    a) 7
    b) 8
    c) 6
    d) `Length`

5.  What will the following code do? `int[] arr = {1, 2, 3}; Console.WriteLine(arr[3]);`
    a) Print `3`.
    b) Print `null`.
    c) Cause a compile-time error.
    d) Cause a run-time `IndexOutOfRangeException`.

6.  The `Length` property of an array returns...
    a) The index of the last element.
    b) The number of elements currently stored.
    c) The total capacity (size) of the array.
    d) The amount of memory the array uses.

7.  Which loop is generally preferred when you need both the index and the value of each element?
    a) `for`
    b) `foreach`
    c) `while`
    d) `do-while`

8.  Which loop is generally preferred for its simplicity when you only need to read the value of each element?
    a) `for`
    b) `foreach`
    c) `while`
    d) `do-while`

9.  Can an array `int[] numbers` hold the value `"hello"`?
    a) Yes, if you cast it.
    b) No, an array can only hold elements of its declared type.
    c) Yes, because all types inherit from `object`.
    d) Only at index 0.

10. What is the value of `names.Length`? `string[] names = { "Tim", "Sue", "Bob" };`
    a) 2
    b) 3
    c) 4
    d) This code is invalid.

11. What is the output of this code?
    ```csharp
    int[] nums = { 10, 20, 30 };
    foreach (int n in nums) { Console.Write(n + " "); }
    ```
    a) `10 20 30`
    b) `0 1 2`
    c) `10 20 30 `
    d) `nums`

12. What does this code do?
    ```csharp
    int[] data = new int[5];
    data[0] = 1; data[1] = 1;
    for (int i = 2; i < data.Length; i++) { data[i] = data[i-1] + data[i-2]; }
    ```
    a) Fills the array with the number 1.
    b) Generates the first 5 numbers of the Fibonacci sequence.
    c) Causes an error.
    d) Sorts the array.

13. To change the third element in an array `arr`, you would use:
    a) `arr[3] = newValue;`
    b) `arr(2) = newValue;`
    c) `arr[2] = newValue;`
    d) `arr.Set(3, newValue);`

14. The primary limitation of an array is...
    a) It is slow to access elements.
    b) It cannot store objects.
    c) It has a fixed size.
    d) It can only store numbers.

15. What is the output of this loop?
    ```csharp
    for (int i = 1; i <= 3; i++) { Console.Write(i); }
    ```
    a) `012` b) `123` c) `1234` d) `0123`

16. An array itself is a...
    a) Reference type (an object).
    b) Value type.
    c) Primitive type.
    d) Static class.

17. In a `for` loop `for (int i = 0; i < arr.Length; i++)`, the condition `i < arr.Length` is crucial to prevent...
    a) An infinite loop.
    b) A compile-time error.
    c) An `IndexOutOfRangeException`.
    d) A `NullReferenceException`.

18. In WPF, a common use for an array is...
    a) To store the application's visual styles.
    b) To provide a fixed collection of items for a `ComboBox` or `ListBox`.
    c) To handle button click events.
    d) To define the window's size.

19. What is the default value of an element in a newly created `int[]` array?
    a) `1` b) `null` c) `0` d) `undefined`

20. What is the default value of an element in a newly created `string[]` array?
    a) `""` (empty string) b) `null` c) ` ` (space) d) `undefined`

---
<details>
  <summary><strong>ANSWER KEY</strong></summary>
  
  1. **b)** It is fixed at the time of creation.
  2. **c)** `int[] numbers = new int[10];`
  3. **b)** Zero-indexed
  4. **c)** 6
  5. **d)** Cause a run-time `IndexOutOfRangeException`.
  6. **c)** The total capacity (size) of the array.
  7. **a)** `for`
  8. **b)** `foreach`
  9. **b)** No, an array can only hold elements of its declared type.
  10. **b)** 3
  11. **c)** `10 20 30 ` (note the trailing space from the code)
  12. **b)** Generates the first 5 numbers of the Fibonacci sequence.
  13. **c)** `arr[2] = newValue;`
  14. **c)** It has a fixed size.
  15. **b)** `123`
  16. **a)** Reference type (an object).
  17. **c)** An `IndexOutOfRangeException`.
  18. **b)** To provide a fixed collection of items for a `ComboBox` or `ListBox`.
  19. **c)** `0`
  20. **b)** `null`
</details>
