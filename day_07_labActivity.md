
## 💻 Lab Activities (6 Hours)

### **Objective**
To implement inheritance hierarchies, understand the flow of constructors, use `public` and `protected` members, and apply these concepts to organize code in Console and WPF applications.

### **Activity 1 (~35 mins): Creating the Base Class**
*   **Concept:** Defining a general, reusable parent class.
*   **Console:** Create a new Console App `Day7_Activity1_Hierarchy`.
    1.  Create a new class file named `Animal.cs`.
    2.  Inside, define the `Animal` class with the following members:
        *   `Name` (public string property)
        *   `Age` (public int property)
        *   `Diet` (protected string property - e.g., "Carnivore", "Herbivore")
        *   `Eat()` (a public `void` method that prints `"{Name} is eating."`)
        *   A constructor that accepts `name` and `age` to initialize the properties.

### **Activity 2 (~35 mins): Creating Derived Classes**
*   **Concept:** Inheriting from a base class and adding specific members.
*   **Console:** In the same project, create two new class files: `Dog.cs` and `Cat.cs`.
    1.  **Dog Class:**
        *   Make it inherit from `Animal`.
        *   Add a `Breed` (public string) property.
        *   Add a `Bark()` method that prints `"Woof!"`.
        *   Create a constructor that accepts `name`, `age`, and `breed`. It must call the base constructor for `name` and `age`.
    2.  **Cat Class:**
        *   Make it inherit from `Animal`.
        *   Add an `IsLazy` (public bool) property.
        *   Add a `Meow()` method that prints `"Meow!"`.
        *   Create a constructor that accepts `name`, `age`, and `isLazy`, calling the base constructor.

### **Activity 3 (~35 mins): Using the Hierarchy**
*   **Concept:** Instantiating and using objects from derived classes.
*   **Console:** In your `Program.cs` `Main` method:
    1.  Create an instance of `Dog`. Set its inherited properties (`Name`, `Age`) via the constructor, as well as its specific property (`Breed`).
    2.  Create an instance of `Cat`. Set its properties.
    3.  Call the inherited `Eat()` method on both your `Dog` and `Cat` objects.
    4.  Call the specific methods (`Bark()` on the dog, `Meow()` on the cat).
    5.  Prove that you can access the `Name` property but cannot access the `Diet` property from `Main`.

### **Activity 4 (~40 mins): The `protected` Modifier in Action**
*   **Concept:** Demonstrating the purpose of `protected`.
*   **Console:**
    1.  In your `Animal` class, set the `Diet` property in the constructor (e.g., all new animals are "Omnivore" by default).
    2.  In your `Dog` class, modify its constructor. After the `base()` call, set the inherited `Diet` property to `"Carnivore"`. This works because `Diet` is `protected`.
    3.  In your `Dog` class, add a new public method `DisplayDiet()` that prints the value of the `Diet` property.
    4.  In `Main`, call `myDog.DisplayDiet()` to prove that the value was changed from within the derived class.

### **Activity 5 (~45 mins): WPF UI for Employee Management**
*   **Concept:** Designing a UI that can adapt to different object types from the same hierarchy.
*   **WPF:** Create a new WPF App `Day7_Activity5_Employees`.
    1.  Design a UI with these elements:
        *   A `ComboBox` named `EmployeeTypeComboBox` with two items: "Manager" and "Developer".
        *   `TextBox`es for common properties: `FirstNameTextBox`, `LastNameTextBox`.
        *   A `StackPanel` for manager-specific fields: a `Label` for "Team Size" and a `TeamSizeTextBox`. Name this panel `ManagerFieldsPanel`.
        *   A `StackPanel` for developer-specific fields: a `Label` for "Programming Language" and a `LanguageTextBox`. Name this panel `DeveloperFieldsPanel`.
        *   A "Create Employee" `Button`.
        *   A `TextBlock` named `ResultTextBlock` to display the created employee's details.

### **Activity 6 (~45 mins): Creating the WPF Class Hierarchy**
*   **Concept:** Building the C# classes that will power the WPF UI.
*   **WPF:** In your WPF project:
    1.  Create an `Employee` base class with `FirstName` and `LastName` properties and a constructor.
    2.  Create a `Manager` class that inherits from `Employee`, adds a `TeamSize` property, and has a corresponding constructor that calls `base()`.
    3.  Create a `Developer` class that inherits from `Employee`, adds a `ProgrammingLanguage` property, and has its own constructor that calls `base()`.
    4.  Add a `GetInfo()` method to each class that returns a formatted string with all of its details.

### **Activity 7 (~45 mins): Driving the Adaptive UI**
*   **Concept:** Using conditional logic to interact with an inheritance hierarchy.
*   **WPF:** In `MainWindow.xaml.cs`:
    1.  Create a `SelectionChanged` event for your `EmployeeTypeComboBox`. In this event, show/hide the `ManagerFieldsPanel` and `DeveloperFieldsPanel` based on the user's selection (`Visibility.Visible` or `Visibility.Collapsed`).
    2.  Create a `Click` event for your "Create Employee" button.
    3.  Inside the click event, use an `if` statement to check the selected item in the `ComboBox`.
        *   If "Manager" is selected, create a `new Manager(...)` object using the data from the text boxes.
        *   If "Developer" is selected, create a `new Developer(...)` object.
    4.  Call the `GetInfo()` method on the newly created object and display the returned string in your `ResultTextBlock`.

### **Activity 8 (~10 mins): Git Submission**
*   **Concept:** Commit your work on inheritance.
*   **Task:** Stage, commit, and push your new projects to GitHub with the message: `"Day 7 Labs: Implemented Inheritance Hierarchies"`.

---
