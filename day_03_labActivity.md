## 💻 Lab Activities (6 Hours)

### **Objective**
To effectively use `for`, `while`, and `do-while` loops to perform repetitive tasks, process sequences of data, and control program flow with `break` and `continue`.

### **Activity 1 (~30 mins): Number Countdown**
*   **Concept:** Basic `for` loop syntax.
*   **Console:** Create `Day3_Activity1_Console`. Write a `for` loop that prints numbers from 10 down to 1.
*   **WPF:** Create `Day3_Activity1_WPF`. Add a `ListBox` and a `Button`. When clicked, the `for` loop should run and add the numbers 1 through 20 to the `ListBox` items.

### **Activity 2 (~35 mins): Multiplication Table Generator**
*   **Concept:** Using a variable from outside the loop as part of the loop's logic.
*   **Console:** Create `Day3_Activity2_Console`. Ask the user for a number. Then, use a `for` loop to print its multiplication table from 1 to 12 (e.g., "5 x 1 = 5", "5 x 2 = 10", ...).
*   **WPF:** Create `Day3_Activity2_WPF`. Use a `TextBox` for the number, a `Button`, and a `ListBox` to display the formatted multiplication table.

### **Activity 3 (~35 mins): Password Guesser**
*   **Concept:** Using a `while` loop that runs an unknown number of times.
*   **Console:** Create `Day3_Activity3_Console`. Hardcode a secret word (e.g., "CSharp"). Use a `while` loop to repeatedly ask the user to guess the word until they get it right. Print a success message after the loop.
*   **WPF:** Create `Day3_Activity3_WPF`. Use a `TextBox` for the guess, a `Button`, and a `TextBlock` for status. On button click, check the guess. If wrong, show "Try Again" in red. If correct, show "Access Granted" in green and disable the `TextBox` and `Button`.

### **Activity 4 (~35 mins): Sum of Numbers**
*   **Concept:** Using a loop to aggregate a value.
*   **Console:** Create `Day3_Activity4_Console`. Ask the user for a positive integer `N`. Use a `while` loop (or a `for` loop) to calculate the sum of all numbers from 1 up to `N` and print the final sum.
*   **WPF:** Create `Day3_Activity4_WPF`. Use a `TextBox` for `N`, a `Button`, and a `TextBlock` to display the calculated sum.

### **Activity 5 (~35 mins): Interactive Menu**
*   **Concept:** The classic use case for a `do-while` loop.
*   **Console Only:** Create `Day3_Activity5_Console`. Design a text menu that displays three options: "1. Say Hello", "2. Say Goodbye", "3. Exit". Use a `do-while` loop to repeatedly show the menu. Use a `switch` statement or `if-else if` block inside the loop to handle the user's choice. The loop should only terminate when the user enters '3'.

### **Activity 6 (~35 mins): Find First Multiple**
*   **Concept:** Using `break` to exit a loop early once a goal is met.
*   **Console Only:** Create `Day3_Activity6_Console`. Ask the user for a number (e.g., 17). Write a `for` loop that iterates from 1 up to 1000. Inside the loop, check if the current number `i` is a multiple of the user's number. If it is, print the number and use `break` to immediately exit the loop.

### **Activity 7 (~35 mins): Print Odd Numbers Only**
*   **Concept:** Using `continue` to skip certain iterations.
*   **Console Only:** Create `Day3_Activity7_Console`. Write a `for` loop that iterates from 1 to 50. Inside the loop, check if the number is even. If it is, use the `continue` statement to skip the `Console.WriteLine`. The result should be a printout of only the odd numbers.

### **Activity 8 (~35 mins): ASCII Art Triangle**
*   **Concept:** Using nested loops (a loop inside another loop).
*   **Console Only:** Create `Day3_Activity8_Console`. Use nested `for` loops to print a right-angled triangle of asterisks (`*`). The outer loop should control the rows, and the inner loop should control the columns (the number of asterisks to print in that row).
    ```
    *
    **
    ***
    ****
    *****
    ```

### **Activity 9 (~35 mins): Dynamic UI Generation**
*   **Concept:** Applying loop logic to programmatically create UI elements.
*   **WPF Only:** Create `Day3_Activity9_WPF`.
    1.  In the XAML, add a `<WrapPanel x:Name="ButtonPanel" />`. A `WrapPanel` automatically arranges its children.
    2.  In the C# code-behind, create a method that runs when a button is clicked.
    3.  Inside this method, write a `for` loop that runs 20 times. In each iteration, create a *new* `Button` object, set its `Content`, and add it to the panel's children: `ButtonPanel.Children.Add(newButton);`.

### **Activity 10 (~20 mins): Git Submission**
*   **Concept:** Committing and pushing all of the day's work.
*   **Instructions:** Use the Visual Studio Terminal to stage, commit, and push all 9 new projects to your remote GitHub repository with a clear commit message like `"Day 3 Labs: Completed all 9 loop activities"`.

---
