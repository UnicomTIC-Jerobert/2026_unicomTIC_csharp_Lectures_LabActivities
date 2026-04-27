## 🎓 Daily Quiz (End of Day)

**Instructions:** Choose the best answer for each question.

1.  Which operator is used to check for exact equality?
    a) `=`
    b) `==`
    c) `!=`
    d) `EQ`

2.  What will be the output of the following code?
    ```csharp
    int x = 10;
    if (x > 10) { Console.WriteLine("A"); }
    else { Console.WriteLine("B"); }
    ```
    a) A
    b) B
    c) Nothing will be printed.
    d) The code will cause an error.

3.  The `&&` operator is known as the logical...
    a) OR operator
    b) NOT operator
    c) AND operator
    d) XOR operator

4.  Which code block will execute if `score` is 85?
    ```csharp
    if (score >= 90) { /* A */ }
    else if (score >= 80) { /* B */ }
    else if (score >= 70) { /* C */ }
    ```
    a) Block A
    b) Block B
    c) Block C
    d) None of them.

5.  To make a hidden `TextBlock` named `ErrorText` visible in WPF, you would use:
    a) `ErrorText.Visibility = Visibility.Visible;`
    b) `ErrorText.Visible = true;`
    c) `ErrorText.Show();`
    d) `ErrorText.IsEnabled = true;`

6.  What is the value of `result`?
    `bool result = (5 < 10) || (20 == 10);`
    a) `true`
    b) `false`
    c) The code is invalid.
    d) `1`

7.  The `else` statement executes when...
    a) The preceding `if` condition is true.
    b) All preceding `if` and `else if` conditions are false.
    c) The preceding `if` condition is false, but an `else if` is true.
    d) Always.

8.  Which operator inverts the value of a boolean?
    a) `~`
    b) `!`
    c) `^`
    d) `NOT`

9.  What is the most appropriate use case for a `switch` statement?
    a) Checking a range of values (e.g., age > 18).
    b) Checking if two different variables are both true.
    c) Checking a single variable against a list of specific, discrete values.
    d) When you only have two possible outcomes.

10. What will be the output?
    ```csharp
    string username = "guest";
    if (username != "admin") { Console.WriteLine("Access Denied"); }
    else { Console.WriteLine("Welcome Admin"); }
    ```
    a) Welcome Admin
    b) Access Denied
    c) An error will occur.
    d) Nothing will be printed.

11. To check if a number `x` is even, the correct condition is:
    a) `x % 2 == 0`
    b) `x / 2 == 0`
    c) `x % 2 == 1`
    d) `x != 0`

12. In WPF, how would you prevent a user from clicking a button named `SubmitButton`?
    a) `SubmitButton.Visibility = Visibility.Collapsed;`
    b) `SubmitButton.IsClickable = false;`
    c) `SubmitButton.IsEnabled = false;`
    d) `SubmitButton.Foreground = Brushes.Gray;`

13. What is the value of `result`?
    `bool result = !(5 > 3);`
    a) `true`
    b) `false`
    c) The code is invalid.
    d) `0`

14. An `if-else if` chain stops checking conditions as soon as...
    a) It finds the first `false` condition.
    b) It finds the first `true` condition.
    c) It has checked all the conditions.
    d) The `else` block is reached.

15. What is the output of `(true && false)`?
    a) `true`
    b) `false`

16. What is the output of `(true || false)`?
    a) `true`
    b) `false`

17. To check if `age` is between 13 and 19 (inclusive), the correct condition is:
    a) `age >= 13 || age <= 19`
    b) `age > 12 && age < 20`
    c) `age >= 13 && age <= 19`
    d) Both b and c are correct.

18. What is wrong with this code? `if (x = 5)`
    a) It should be `if (x == 5)`. The single `=` is for assignment, not comparison.
    b) Parentheses are not needed.
    c) There is nothing wrong with it.
    d) It should use single quotes: `if (x == '5')`.

19. In WPF, changing a `TextBlock`'s `Foreground` property will change its...
    a) Background color
    b) Font size
    c) Text color
    d) Visibility

20. What is the primary reason to use conditional logic in programming?
    a) To make the code run faster.
    b) To make programs interactive and able to respond differently to different situations.
    c) To organize code into methods.
    d) To store data in variables.

---
<details>
  <summary><strong>ANSWER KEY</strong></summary>
  
  1. **b)** `==`
  2. **b)** B
  3. **c)** AND operator
  4. **b)** Block B
  5. **a)** `ErrorText.Visibility = Visibility.Visible;`
  6. **a)** `true` (because `5 < 10` is true, the OR condition is met)
  7. **b)** All preceding `if` and `else if` conditions are false.
  8. **b)** `!`
  9. **c)** Checking a single variable against a list of specific, discrete values.
  10. **b)** Access Denied
  11. **a)** `x % 2 == 0`
  12. **c)** `SubmitButton.IsEnabled = false;`
  13. **b)** `false` (`5 > 3` is true, and `!` inverts it to false)
  14. **b)** It finds the first `true` condition.
  15. **b)** `false`
  16. **a)** `true`
  17. **d)** Both b and c are correct. (Both logically define the same range of integers).
  18. **a)** It should be `if (x == 5)`. The single `=` is for assignment, not comparison.
  19. **c)** Text color
  20. **b)** To make programs interactive and able to respond differently to different situations.
</details>
