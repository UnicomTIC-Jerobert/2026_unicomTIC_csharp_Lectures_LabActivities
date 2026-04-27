## 🎓 Daily Quiz (End of Day)

**Instructions:** Choose the best answer for each question.

1.  What is the main benefit of using methods in programming?
    a) They make the program run faster.
    b) They allow you to reuse code and make it more organized.
    c) They are the only way to get input from a user.
    d) They increase the file size of the application.

2.  In the method signature `public bool IsValid(int value)`, what is `bool`?
    a) The access modifier
    b) The method name
    c) A parameter
    d) The return type

3.  The `void` keyword in a method signature means...
    a) The method cannot be called.
    b) The method returns a `null` value.
    c) The method does not return a value.
    d) The method can accept any type of parameter.

4.  What is the term for the actual values passed to a method when it is called?
    a) Parameters
    b) Arguments
    c) Variables
    d) Types

5.  What keyword is used to send a value back from a method?
    a) `send`
    b) `give`
    c) `return`
    d) `result`

6.  A variable declared inside a method is said to have...
    a) Global scope
    b) Class scope
    c) Local scope
    d) No scope

7.  Consider this method: `public int GetNumber() { return 10; }`. What is the value of `x` after this line? `int x = GetNumber();`
    a) `0`
    b) `10`
    c) `null`
    d) The code will cause an error.

8.  What is **Method Overloading**?
    a) Creating a method that is too long and complex.
    b) Creating multiple methods with the same name but different parameter lists.
    c) Calling a method from within itself.
    d) Creating a method that returns another method.

9.  Which of the following is a VALID overload for `void DoWork(int x)`?
    a) `int DoWork(int x)`
    b) `void DoWork(int y)`
    c) `void DoWork(string x)`
    d) `private void DoWork(int x)`

10. The process of restructuring code for better organization without changing its functionality is called...
    a) Compiling
    b) Debugging
    c) Refactoring
    d) Overloading

11. What is wrong with this code?
    ```csharp
    public static void Add(int a, int b) { int sum = a + b; }
    int result = Add(5, 3);
    ```
    a) The method should not be `static`.
    b) The method has a `void` return type but is being used as if it returns a value.
    c) The parameters `a` and `b` cannot be `int`.
    d) There is nothing wrong.

12. In the signature `void PrintMessage(string message)`, `message` is a(n)...
    a) Argument
    b) Return type
    c) Parameter
    d) Method name

13. What is the output of this code?
    ```csharp
    void Main() { int num = 5; AlterNumber(num); Console.WriteLine(num); }
    void AlterNumber(int x) { x = 10; }
    ```
    a) `5`
    b) `10`
    c) An error will occur.
    d) `0`

14. The practice of making an event handler (like `Button_Click`) short and having it call other methods to do the work is an example of...
    a) Method overloading
    b) Variable scope
    c) Separation of Concerns
    d) Recursion

15. What will this method return?
    ```csharp
    public static string CheckValue(int val) { if (val > 10) return "High"; else return "Low"; }
    ```
    a) A `bool`
    b) An `int`
    c) A `string`
    d) `void`

16. Which of the following is NOT a good reason to create a method?
    a) The code is used in multiple places.
    b) The code block is very complex and a good name would make it easier to understand.
    c) The code is only a single, simple line.
    d) To separate UI logic from business logic.

17. If a method starts with `private`, it means...
    a) It can only be called from within the same class.
    b) It cannot have any parameters.
    c) It must return `void`.
    d) The method is not finished.

18. What is the return type of the `Main` method in a console application?
    a) `int`
    b) `string`
    c) `void` or `int`
    d) It has no return type.

19. Which method call is valid for the signature `void SetConfig(string name, int version, bool enabled)`?
    a) `SetConfig("App", 1, true)`
    b) `SetConfig("App", 1)`
    c) `SetConfig(1, "App", true)`
    d) `SetConfig(true, 1, "App")`

20. A well-named method like `IsUserAuthenticated()` primarily improves code...
    a) Performance
    b) Readability
    c) Security
    d) Memory usage

---
<details>
  <summary><strong>ANSWER KEY</strong></summary>
  
  1. **b)** They allow you to reuse code and make it more organized.
  2. **d)** The return type
  3. **c)** The method does not return a value.
  4. **b)** Arguments
  5. **c)** `return`
  6. **c)** Local scope
  7. **b)** `10`
  8. **b)** Creating multiple methods with the same name but different parameter lists.
  9. **c)** `void DoWork(string x)` (Different parameter type. Changing only the return type or parameter name is NOT a valid overload).
  10. **c)** Refactoring
  11. **b)** The method has a `void` return type but is being used as if it returns a value.
  12. **c)** Parameter
  13. **a)** `5` (Because `int` is a value type, the original `num` variable is not changed by the method).
  14. **c)** Separation of Concerns
  15. **c)** A `string`
  16. **c)** The code is only a single, simple line.
  17. **a)** It can only be called from within the same class.
  18. **c)** `void` or `int` (It can return an exit code).
  19. **a)** `SetConfig("App", 1, true)` (Matches the parameter types and order).
  20. **b)** Readability
</details>
