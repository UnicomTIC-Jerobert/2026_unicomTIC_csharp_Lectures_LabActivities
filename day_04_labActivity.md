## 💻 Lab Activities (6 Hours)

### **Objective**
To master creating and calling methods, understand the difference between `void` and value-returning methods, pass data using parameters, and refactor existing code for better organization.

### **Activity 1 (~30 mins): Simple Greeter (`void` methods)**
*   **Concept:** Creating a simple method that performs an action without returning data.
*   **Console:** Create `Day4_Activity1_Console`. In `Program.cs`, create a `static void SayHello()` method that prints "Hello, World!". Call this method from `Main`.
*   **WPF:** Create `Day4_Activity1_WPF`. In `MainWindow.xaml.cs`, create a `private void ShowGreeting()` method that displays a `MessageBox` with "Welcome to the application!". In the main `Button_Click` event, call `ShowGreeting()`.

### **Activity 2 (~35 mins): Methods with Parameters**
*   **Concept:** Passing data into a method to change its behavior.
*   **Console:** In `Day4_Activity1_Console`, create a new method `static void GreetUser(string name)` that prints "Hello, [name]!". From `Main`, ask the user for their name and then call this method, passing the user's input as an argument.
*   **WPF:** In `Day4_Activity1_WPF`, add a `TextBox` to the UI. Modify the `Button_Click` to get the name from the `TextBox`. Create a new method `private void ShowPersonalizedGreeting(string name)` that shows a `MessageBox` saying "Welcome, [name]!". Call this method from the `Button_Click`.

### **Activity 3 (~35 mins): Basic Calculator (`return` values)**
*   **Concept:** Creating methods that perform a calculation and return the result.
*   **Console:** Create `Day4_Activity3_Console`. Create four static methods: `Add(int a, int b)`, `Subtract(int a, int b)`, `Multiply(int a, int b)`, and `Divide(double a, double b)`. Each method should perform the calculation and `return` the result. In `Main`, call each of these methods with sample numbers and print their results.
*   **WPF:** Create `Day4_Activity3_WPF`. Design a calculator UI. The `Button_Click` event for the "Add" button should get the numbers, call a separate `private int Add(int a, int b)` method, and display the returned result in a `TextBlock`.

### **Activity 4 (~35 mins): String Manipulator**
*   **Concept:** Writing methods that process and return strings.
*   **Console Only:** Create `Day4_Activity4_Console`.
    1.  Write a method `public static string ReverseString(string text)` that takes a string and returns a new string with the characters in reverse order. (Hint: a `for` loop that goes backwards through the string is one way).
    2.  Write a method `public static bool IsPalindrome(string text)` that returns `true` if a word is the same forwards and backwards (e.g., "racecar") and `false` otherwise. This method can call your `ReverseString` method!
    3.  In `Main`, test both methods with various strings.

### **Activity 5 (~35 mins): Refactoring Day 3's Code**
*   **Concept:** Improving existing code by extracting logic into methods.
*   **Console:** Open your `Day3_Activity2_Console` (Multiplication Table). The logic is currently inside `Main`. Create a new method `public static void PrintMultiplicationTable(int number)` and move the entire `for` loop and printing logic into it. Your `Main` method should now just get the user's input and make a single call to your new method.
*   **WPF:** Open your `Day3_Activity3_WPF` (Password Guesser). The logic is in the `Button_Click`. Create a `private bool CheckPassword(string attempt)` method that returns `true` if the password is correct and `false` otherwise. Your `Button_Click` should now call this method and then use an `if` statement to decide what to do with the UI.

### **Activity 6 (~30 mins): Temperature Converter Library**
*   **Concept:** Creating a "library" of related functions.
*   **Console Only:** Create `Day4_Activity6_Console`. Create a static class `public static class TempConverter`. Inside this class, write two methods:
    1.  `public static double CelsiusToFahrenheit(double celsius)`
    2.  `public static double FahrenheitToCelsius(double fahrenheit)`
    In `Main`, test your library by calling `TempConverter.CelsiusToFahrenheit(25)` and `TempConverter.FahrenheitToCelsius(77)` and printing the results.

### **Activity 7 (~30 mins): UI Logic Separation**
*   **Concept:** A key WPF skill: keeping event handlers clean.
*   **WPF Only:** Create `Day4_Activity7_WPF`. Build a simple BMI calculator UI (from Day 2). The `Button_Click` handler should be very short:
    1.  Create a method `private void UpdateUi()` that does all the work: it gets the text, parses it, calls the calculation method, and updates the `TextBlock`.
    2.  Create a method `private double CalculateBmi(double weight, double height)` that only does the math and returns the result.
    3.  Your `Button_Click` event should now only contain one line: `UpdateUi();`.

### **Activity 8 (~30 mins): Method Overloading**
*   **Concept:** Creating multiple methods with the same name but different parameters.
*   **Console Only:** Create `Day4_Activity8_Console`.
    1.  Write a method `public static void Greet()` that prints "Hello, guest!".
    2.  Write a second method `public static void Greet(string name)` that prints "Hello, [name]!".
    3.  Write a third method `public static void Greet(string name, int times)` that uses a `for` loop to print "Hello, [name]!" the specified number of times.
    4.  In `Main`, call all three versions of the `Greet` method to see how C# automatically picks the correct one based on the arguments you provide.

### **Activity 9 (~30 mins): The Validator Class**
*   **Concept:** Building a set of reusable validation functions.
*   **Console Only:** Create `Day4_Activity9_Console`. Create a static class `public static class Validator`. Inside, create these methods:
    1.  `public static bool IsPositive(double number)`: Returns `true` if `number > 0`.
    2.  `public static bool IsInRange(int number, int min, int max)`: Returns `true` if the number is between min and max (inclusive).
    3.  `public static bool IsPasswordValid(string password)`: Returns `true` if the password is at least 8 characters long.
    In `Main`, test each of your validation methods.

### **Activity 10 (~20 mins): Git Submission**
*   **Concept:** Committing your organized, method-driven code.
*   **Instructions:** Stage, commit, and push all 9 new projects for the day to your remote GitHub repository. Use a descriptive commit message like `"Day 4 Labs: Completed method and function activities"`.

---
