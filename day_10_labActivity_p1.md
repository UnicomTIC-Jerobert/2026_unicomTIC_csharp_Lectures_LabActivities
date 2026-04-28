
## 💻 Lab Activities (6 Hours) - Zoo Management Project

### **Objective**
To design and implement a complete object-oriented system from scratch, applying encapsulation, inheritance, polymorphism, and interfaces to solve a complex problem.

### **Part 1: The Console Logic Core (Activities 1-7)**

#### **Activity 1 (~30 mins): Defining the Core Contracts**
*   **Concept:** Starting with the highest level of abstraction.
*   **Task:** Create a new Console App `Day10_ZooManager_Console`.
    1.  Create an `abstract` class file `Animal.cs`.
        *   Properties: `public string Name { get; set; }`, `public int Age { get; set; }`.
        *   Constructor: to set the `Name` and `Age`.
        *   Abstract Methods: `public abstract string MakeSound();` and `public abstract string Move();`. (Abstract methods have no body `{}`).
    2.  Create an interface file `IFlyable.cs`.
        *   Method Signature: `string Fly();`.

#### **Activity 2 (~30 mins): The First Level of Inheritance**
*   **Concept:** Creating intermediate abstract classes.
*   **Task:** In the same project:
    1.  Create an `abstract` class `Mammal.cs` that inherits from `Animal`.
        *   Add a property: `public string FurColor { get; set; }`.
        *   Create a constructor that accepts `name`, `age`, and `furColor`, and calls the `base(name, age)` constructor.
    2.  Create an `abstract` class `Bird.cs` that inherits from `Animal`.
        *   Add a property: `public double WingSpan { get; set; }`.
        *   Create a constructor that accepts `name`, `age`, and `wingSpan`, and calls the `base` constructor.

#### **Activity 3 (~35 mins): Creating Concrete `Mammal` Classes**
*   **Concept:** Implementing abstract methods from a base class.
*   **Task:**
    1.  Create a `Lion.cs` class that inherits from `Mammal`.
        *   Create a constructor that calls the `base` constructor.
        *   `override` the `MakeSound()` method to return `"Roar!"`.
        *   `override` the `Move()` method to return `"Prowling on four paws."`.
    2.  Create a `Monkey.cs` class that inherits from `Mammal`.
        *   Create a constructor.
        *   `override` `MakeSound()` to return `"Ooh ooh aah aah!"`.
        *   `override` `Move()` to return `"Swinging from branches."`.

#### **Activity 4 (~35 mins): Creating Concrete `Bird` Classes**
*   **Concept:** Implementing both abstract methods and interfaces.
*   **Task:**
    1.  Create an `Eagle.cs` class that inherits from `Bird` **and** implements `IFlyable`.
        *   Create a constructor.
        *   `override` `MakeSound()` to return `"Screech!"`.
        *   `override` `Move()` to return `"Soaring through the sky."`.
        *   Implement the `Fly()` method from `IFlyable` to return `"The eagle flaps its massive wings and takes flight."`.
    2.  Create a `Penguin.cs` class that inherits from `Bird` (but does **not** implement `IFlyable`).
        *   Create a constructor.
        *   `override` `MakeSound()` to return `"Squawk!"`.
        *   `override` `Move()` to return `"Waddling on the ice."`.

#### **Activity 5 (~35 mins): The `Zoo` Class**
*   **Concept:** Encapsulating the main collection and logic.
*   **Task:** Create a `Zoo.cs` class.
    1.  Add a `private List<Animal> animals = new List<Animal>();` as a field.
    2.  Add a `public void AddAnimal(Animal animal)` method that adds an animal to the list.
    3.  Add a `public void TriggerAllSounds()` method that loops through the `animals` list and prints the result of each animal's `MakeSound()` method.
    4.  Add a `public void TriggerAllMovement()` method that does the same for the `Move()` method.

#### **Activity 6 (~30 mins): The `IFlyable` Demonstration**
*   **Concept:** Using interfaces to work with a specific capability.
*   **Task:** In your `Zoo.cs` class:
    1.  Add a `public void PerformFlightShow()` method.
    2.  Inside this method, loop through the `animals` list.
    3.  Use the `is` keyword to check if the current animal is flyable: `if (animal is IFlyable)`.
    4.  If it is, cast it and call the `Fly()` method: `IFlyable flyingAnimal = (IFlyable)animal; Console.WriteLine(flyingAnimal.Fly());`.

#### **Activity 7 (~30 mins): Bringing It All Together in Console**
*   **Concept:** Using the completed OOP system.
*   **Task:** In your `Program.cs` `Main` method:
    1.  Create an instance of your `Zoo` class.
    2.  Create instances of `Lion`, `Monkey`, `Eagle`, and `Penguin`.
    3.  Use the `zoo.AddAnimal()` method to add all of them to the zoo.
    4.  Call `zoo.TriggerAllSounds()`, `zoo.TriggerAllMovement()`, and `zoo.PerformFlightShow()` and observe the polymorphic behavior.

---

### **Part 2: The WPF Graphical User Interface (Activities 8-10)**

#### **Activity 8 (~45 mins): WPF UI Design**
*   **Concept:** Designing a UI to manage and interact with a collection of polymorphic objects.
*   **Task:** Create `Day10_ZooManager_WPF`.
    1.  Design a UI with:
        *   A `ComboBox` to select the type of animal to add ("Lion", "Monkey", "Eagle", "Penguin").
        *   `TextBox`es for `Name` and `Age`.
        *   A "Add Animal to Zoo" `Button`.
        *   A `ListBox` named `ZooRosterListBox` to display all animals currently in the zoo.
        *   Action buttons: "All Make Sound", "All Move", "Perform Flight Show".
        *   A large `TextBox` or `TextBlock` named `ActionLog` to display the results of the actions.

#### **Activity 9 (~45 mins): Wiring up the UI Backend**
*   **Concept:** Integrating the OOP logic classes into a WPF application.
*   **Task:** In `MainWindow.xaml.cs`:
    1.  Add all your class files (`Animal.cs`, `Mammal.cs`, `Lion.cs`, `IFlyable.cs`, `Zoo.cs`, etc.) to the WPF project.
    2.  Create a private instance of your `Zoo` class as a member variable: `private Zoo myZoo = new Zoo();`.
    3.  Implement the "Add Animal" button's `Click` event. Use a `switch` statement on the `ComboBox`'s selection to create the correct type of animal (`new Lion(...)`, etc.), then add it to `myZoo` and update the `ZooRosterListBox`. (Override `ToString()` in your animal classes for a nice display!).

#### **Activity 10 (~30 mins): Implementing the Action Buttons**
*   **Concept:** Making the UI drive the polymorphic behavior.
*   **Task:**
    1.  The challenge with the action buttons is getting the string results back from the `Zoo` class. Modify your `Zoo` class methods (`TriggerAllSounds`, etc.) so they `return` a `List<string>` of the results instead of printing them to the console.
    2.  Implement the `Click` event for the "All Make Sound" button. It should call `myZoo.TriggerAllSounds()`, then loop through the returned list of strings and display them in the `ActionLog`.
    3.  Do the same for the "All Move" and "Perform Flight Show" buttons.
    4.  Finally, perform the **Git Submission** for the day's work.

---
