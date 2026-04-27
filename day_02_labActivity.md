## 💻 Lab Activities (6 Hours)

### **Objective**
Master the use of `if`, `else if`, `else`, and logical operators (`&&`, `||`) to create applications that respond dynamically to different inputs in both Console and WPF.

### **Activity 1 (~45 mins): Voter Eligibility Checker**
*   **Concept:** A simple `if-else` statement.
*   **Console:** Create `Day2_Activity1_Console`. Ask for the user's age. If the age is 18 or greater, print "You are eligible to vote." Otherwise, print "You are not eligible to vote."
*   **WPF:** Create `Day2_Activity1_WPF`. Use a `TextBox` for age and a `Button`. When clicked, display the result in a `TextBlock`, changing its color to green for "eligible" and red for "not eligible."

### **Activity 2 (~50 mins): Student Marks Grader**
*   **Concept:** Using an `if-else if-else` chain for categorization.
*   **Console:** Create `Day2_Activity2_Console`. Ask for a student's score (0-100). Implement the following grading scale:
    *   90-100: "Grade: A"
    *   80-89: "Grade: B"
    *   70-79: "Grade: C"
    *   60-69: "Grade: D"
    *   Below 60: "Grade: F"
    *   Handle invalid inputs (e.g., scores below 0 or above 100).
*   **WPF:** Create `Day2_Activity2_WPF`. Use a `TextBox` for the score and a `Button`. Display the resulting letter grade in a `TextBlock`. The `TextBlock` should have a large font size and a distinct color for each grade (e.g., A=Green, B=Blue, F=Red).

### **Activity 3 (~50 mins): BMI Calculator & Categorizer**
*   **Concept:** Combining formulas (`double`), type conversion, and `if-else if` chains.
*   **Console:** Create `Day2_Activity3_Console`.
    *   Ask for weight in kilograms (e.g., 70.5) and height in meters (e.g., 1.75).
    *   Calculate BMI using the formula: `BMI = weight / (height * height)`.
    *   Categorize and print the result based on the BMI value:
        *   Below 18.5: "Underweight"
        *   18.5 to 24.9: "Normal weight"
        *   25 to 29.9: "Overweight"
        *   30 or above: "Obesity"
*   **WPF:** Create `Day2_Activity3_WPF`. Design a UI with `TextBox`es for weight and height. A `Button` should trigger the calculation and display *both* the numerical BMI value and the text-based category in a `TextBlock`.

### **Activity 4 (~50 mins): Secure Login Form**
*   **Concept:** Using the logical `&&` (AND) operator to check multiple conditions simultaneously.
*   **WPF Only:** Create `Day2_Activity4_WPF`.
    *   Design a login form with a `TextBox` for username and a `PasswordBox` for the password.
    *   When the "Login" button is clicked, check if the username is `"Admin"` **AND** the password is `"P@ssw0rd123"`.
    *   If both are true, display a green "Login Successful" message and disable the text boxes and login button.
    *   Otherwise, display a red "Access Denied" message.

### **Activity 5 (~50 mins): Ticket Discount Calculator**
*   **Concept:** Using the logical `||` (OR) operator.
*   **Console:** Create `Day2_Activity5_Console`.
    *   Set a base ticket price, e.g., `double basePrice = 12.50;`.
    *   Ask the user for their age and if they are a student (ask them to type "yes" or "no").
    *   If the age is 12 or under, **OR** if the age is 65 or over, apply a 50% discount.
    *   If they are a student ("yes"), apply a 25% discount.
    *   **Note:** The senior/child discount should take priority. Print the final ticket price.
*   **WPF:** Create `Day2_Activity5_WPF`. Use a `TextBox` for age and a `CheckBox` for "Is Student?". A button calculates and displays the final price.

### **Activity 6 (~50 mins): Leap Year Checker**
*   **Concept:** Writing a complex logical condition with `&&` and `||`.
*   **Rule:** A year is a leap year if it is divisible by 4, except for end-of-century years, which must be divisible by 400. (e.g., 2000 was a leap year, but 1900 was not).
*   **The Logic:** `(year % 4 == 0 && year % 100 != 0) || (year % 400 == 0)`
*   **Console:** Create `Day2_Activity6_Console`. Ask for a year, apply the logic, and print either "It is a leap year." or "It is not a leap year."
*   **WPF:** Create `Day2_Activity6_WPF`. A `TextBox` for the year and a `Button` shows the result in a `TextBlock`.

### **Activity 7 (~25 mins): Git Submission**
*   **Concept:** Committing the day's work to version control.
*   **Instructions:**
    1.  Open the Terminal in Visual Studio.
    2.  Stage all your new projects for the day.
        ```bash
        git add .
        ```
    3.  Commit the changes with a clear, descriptive message.
        ```bash
        git commit -m "Day 2 Labs: Completed all 6 conditional logic activities"
        ```
    4.  Push your commit to your remote GitHub repository.
        ```bash
        git push
        ```

---

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
