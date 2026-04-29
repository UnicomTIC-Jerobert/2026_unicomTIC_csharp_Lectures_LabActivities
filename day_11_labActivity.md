## 💻 Lab Activities (6 Hours)

### **Objective**
To master the declaration, instantiation, and manipulation of arrays. To use `for` and `foreach` loops to process array data and apply these concepts in both Console and WPF applications.

### **Activity 1 (~30 mins): Declaration and Initialization**
*   **Concept:** Basic array syntax.
*   **Console:** Create `Day11_Activity1_Arrays`.
    1.  Declare and instantiate an integer array named `studentAges` with a size of 5.
    2.  Declare and initialize a string array named `productNames` with the values: "Laptop", "Mouse", "Keyboard", "Monitor".
    3.  Print the `Length` of both arrays to the console.

### **Activity 2 (~35 mins): Accessing and Modifying Elements**
*   **Concept:** Using index notation to read and write array data.
*   **Console:** In the same project:
    1.  Using the `studentAges` array, assign a different age to each of the 5 elements using its index (e.g., `studentAges[0] = 21;`).
    2.  Print the value of the **first** and the **last** element to the console.
    3.  Change the value of the element at index `2` to a new age.
    4.  Print the new value at index `2` to confirm it was changed.

### **Activity 3 (~35 mins): Iterating with a `for` Loop**
*   **Concept:** The standard way to process an array when the index is important.
*   **Console:** Create `Day11_Activity3_Loops`.
    1.  Create an array of your five favorite movie titles.
    2.  Write a `for` loop that iterates from `0` to `movies.Length - 1`.
    3.  Inside the loop, print out a numbered list, e.g., `"1. Inception"`, `"2. The Matrix"`, etc. (Hint: `i + 1`).

### **Activity 4 (~35 mins): Iterating with a `foreach` Loop**
*   **Concept:** The simpler, more readable loop for when you don't need the index.
*   **Console:** In the same project:
    1.  Create an array of doubles representing prices: `19.99`, `4.50`, `120.00`, `8.75`.
    2.  Write a `foreach` loop to iterate through the prices.
    3.  Inside the loop, calculate a 10% tax for each price and print the original price and the price including tax.

### **Activity 5 (~40 mins): Populating an Array from User Input**
*   **Concept:** Combining I/O, loops, and arrays.
*   **Console:** Create `Day11_Activity5_UserInput`.
    1.  Ask the user "How many friends do you have?". Read their input and create a `string` array of that size.
    2.  Use a `for` loop to ask the user to enter the name of each friend, and store each name in the array at the correct index.
    3.  After the first loop finishes, use a `foreach` loop to print out "Your friends are: [name1], [name2], ...".

### **Activity 6 (~40 mins): Array Data Analysis**
*   **Concept:** Using loops to perform calculations on numeric arrays.
*   **Console:** Create `Day11_Activity6_Analysis`.
    1.  Create an integer array with at least 10 different numbers (positive and negative).
    2.  Write code to find the **Sum**, **Average**, **Minimum**, and **Maximum** values in the array.
    3.  You will need to declare variables for `sum`, `min`, `max` *before* your loop, and then update them *inside* the loop as you iterate through the numbers.

### **Activity 7 (~40 mins): Populating a WPF `ComboBox`**
*   **Concept:** Using an array as a data source for a UI element.
*   **WPF:** Create `Day11_Activity7_WPF_UI`.
    1.  Design a UI with a `ComboBox`, a `Button`, and a `TextBlock`.
    2.  In `MainWindow.xaml.cs`, create a `private string[] categories = { "Electronics", "Books", "Home & Garden", "Toys" };` as a member variable.
    3.  In the `Button`'s `Click` event, use a `foreach` loop to iterate through your `categories` array and add each item to the `ComboBox.Items`.
    4.  Create a `SelectionChanged` event for the `ComboBox`. When the user selects an item, display their choice in the `TextBlock`.

### **Activity 8 (~40 mins): Displaying an Array of Objects in WPF**
*   **Concept:** Bridging OOP with collection management in a UI.
*   **WPF:** In the same project:
    1.  Create a simple `Product` class with `Name` (string) and `Price` (double) properties. Override `ToString()` to return `"{Name} - ${Price}"`.
    2.  In `MainWindow.xaml.cs`, create an array of `Product` objects: `private Product[] productInventory = new Product[3];`.
    3.  In the `MainWindow` constructor, create and add three `new Product(...)` objects to your `productInventory` array.
    4.  Add a second `ListBox` to your UI. Add a new `Button` ("Load Inventory").
    5.  When this new button is clicked, loop through your `productInventory` array and add each `Product` object to the `ListBox`. Because you overrode `ToString()`, it will display nicely.

### **Activity 9 (~15 mins): Git Submission**
*   **Task:** Stage, commit, and push your new projects to GitHub with the message: `"Day 11 Labs: Array Fundamentals"`.

---
