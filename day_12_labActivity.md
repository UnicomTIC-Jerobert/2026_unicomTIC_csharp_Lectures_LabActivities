## 💻 Lab Activities (6 Hours)

### **Objective**
To understand the advantages of `List<T>` over arrays, master its common methods (`Add`, `Remove`, `Insert`, etc.), and use it to manage dynamic collections of both simple types and custom objects in Console and WPF applications.

### **Activity 1 (~30 mins): Basic List Creation and `Add`**
*   **Concept:** Transitioning from array syntax to list syntax.
*   **Console:** Create `Day12_Activity1_Lists`.
    1.  Add `using System.Collections.Generic;` at the top of `Program.cs`.
    2.  Create an empty `List<string>` called `shoppingList`.
    3.  Use the `.Add()` method to add "Milk", "Eggs", "Bread", and "Apples" to the list.
    4.  Print the `.Count` of the list.
    5.  Use a `foreach` loop to print each item in the list.

### **Activity 2 (~35 mins): Removing Items**
*   **Concept:** Using `.Remove()` and `.RemoveAt()`.
*   **Console:** In the same project:
    1.  After populating your `shoppingList`, use `.Remove("Eggs");` to remove the eggs by value.
    2.  Print the list again to confirm it's gone.
    3.  Now, use `.RemoveAt(0);` to remove the item at the first index ("Milk").
    4.  Print the list a final time to see the result.

### **Activity 3 (~35 mins): Inserting and Checking with `Contains`**
*   **Concept:** Using `.Insert()` and `.Contains()`.
*   **Console:** Create `Day12_Activity3_Advanced`.
    1.  Create a `List<int>` with the numbers `10, 20, 40, 50`.
    2.  Use `.Insert(2, 30);` to add the number 30 into the correct position.
    3.  Use an `if` statement with `myList.Contains(40)` to check if the number 40 is in the list and print a confirmation message.
    4.  Use another `if` statement to check for the number `99`.

### **Activity 4 (~40 mins): Dynamic To-Do List**
*   **Concept:** Building an interactive program using a `List<T>`.
*   **Console:** Create `Day12_Activity4_ToDo`.
    1.  Create an empty `List<string>` called `tasks`.
    2.  Create a `while(true)` loop to make the program run continuously.
    3.  Inside the loop, display a menu: "1. Add Task", "2. View Tasks", "3. Remove Task", "4. Exit".
    4.  Based on the user's choice:
        *   **Add:** Ask for a task description and `.Add()` it to the list.
        *   **View:** Loop through the list and print each task with its number (index + 1).
        *   **Remove:** Ask for the task number to remove and use `.RemoveAt(number - 1);`.
        *   **Exit:** Use `break;` to exit the `while` loop.

### **Activity 5 (~40 mins): List of Objects**
*   **Concept:** The most common use case: managing a collection of custom objects.
*   **Console:** Create `Day12_Activity5_Objects`.
    1.  Create a `Student` class with `Name` and `Grade` properties. Override `ToString()` to return a formatted string.
    2.  In `Main`, create a `List<Student>`.
    3.  Create and `.Add()` at least three `new Student(...)` objects to the list.
    4.  Write a `foreach` loop that iterates through the list and prints each student.
    5.  Write a second loop that finds and prints only the students who have a `Grade` greater than 85.

### **Activity 6 (~40 mins): WPF Dynamic `ListBox`**
*   **Concept:** Using a `List<T>` as a dynamic data source for a WPF `ListBox`.
*   **WPF:** Create `Day12_Activity6_WPF`.
    1.  Design a UI with a `TextBox`, an "Add Item" `Button`, a "Remove Selected" `Button`, and a `ListBox`.
    2.  In `MainWindow.xaml.cs`, create a `private List<string> items = new List<string>();` as a member variable.
    3.  The "Add Item" button should get the text from the `TextBox`, `.Add()` it to your `items` list, and then call a helper method `UpdateListBox()`.
    4.  The "Remove Selected" button should get the `SelectedItem` from the `ListBox`, `.Remove()` it from your `items` list, and then call `UpdateListBox()`.
    5.  The `UpdateListBox()` method should clear the `ListBox.Items` and then loop through your `items` list to repopulate it.

### **Activity 7 (~40 mins): WPF Contact Book**
*   **Concept:** A mini-project combining OOP and `List<T>` in a UI.
*   **WPF:** Create `Day12_Activity7_Contacts`.
    1.  Create a `Contact` class (`Name`, `PhoneNumber`). Override `ToString()`.
    2.  Design a UI to add and view contacts. It needs `TextBox`es for name and phone, an "Add Contact" button, and a `ListBox` to display the contacts.
    3.  In the code-behind, create a `private List<Contact> contacts = new List<Contact>();`.
    4.  The "Add Contact" button should create a `new Contact` object from the `TextBox`es, add it to the `contacts` list, and update the `ListBox`.

### **Activity 8 (~15 mins): Git Submission**
*   **Task:** Stage, commit, and push your new projects to GitHub with the message: `"Day 12 Labs: Generic List<T> Fundamentals"`.

---
