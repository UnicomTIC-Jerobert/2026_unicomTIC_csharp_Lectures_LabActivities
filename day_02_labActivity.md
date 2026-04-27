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
