# Week 2, Day 2: Inheritance

## 📖 Lecture Notes (1 Hour)

### 1. Introduction: Building on What Exists
Yesterday, we learned to create blueprints (classes) for objects. But what if we have classes that are very similar?

Imagine a software system for a company. You might have a `Manager` class, an `Intern` class, and a `Developer` class. All of them share common properties (`FirstName`, `LastName`, `EmployeeID`) and behaviors (`ClockIn()`, `Work()`). Writing this code in all three classes would violate the **DRY (Don't Repeat Yourself)** principle.

Inheritance allows us to define a common, more general class (e.g., `Employee`) and then create more specific classes (`Manager`, `Intern`) that **inherit** all the common properties and methods.

### 2. The Core Idea: The "Is-A" Relationship
Inheritance models the **"is-a"** relationship.
*   A `Manager` **is an** `Employee`.
*   A `Car` **is a** `Vehicle`.
*   A `Dog` **is an** `Animal`.

This relationship is key. The more specific class has everything the general class has, *plus* some extra features of its own.

*   **Base Class (or Parent/Superclass):** The general class that is being inherited from (e.g., `Employee`).
*   **Derived Class (or Child/Subclass):** The specific class that inherits from the base class (e.g., `Manager`).

### 3. Inheritance Syntax in C#
We use a colon (`:`) in the class definition to specify which class we are inheriting from.

```csharp
// 1. The Base Class (Parent)
public class Employee
{
    public string FirstName { get; set; }
    public string LastName { get; set; }
    public int EmployeeID { get; set; }

    public void Work()
    {
        Console.WriteLine($"{FirstName} {LastName} is working.");
    }
}

// 2. The Derived Class (Child)
// Manager inherits all public members from Employee.
public class Manager : Employee
{
    // A Manager "is an" Employee, but also has a team.
    // This is a property specific to the Manager class.
    public int TeamSize { get; set; }
}

// 3. How to use it:
Manager myManager = new Manager();
myManager.FirstName = "Jane";      // Inherited from Employee
myManager.LastName = "Doe";        // Inherited from Employee
myManager.EmployeeID = 101;        // Inherited from Employee
myManager.TeamSize = 10;           // Specific to Manager

myManager.Work();                  // Inherited method from Employee
```

### 4. What is Inherited? Access Modifiers
Not everything from a base class is accessible to a derived class. It depends on the access modifier.
*   **`public` members:** Are fully inherited and can be accessed by the derived class and from anywhere else.
*   **`private` members:** Are **NOT** inherited. They are completely hidden from the derived class. A child class has no knowledge of its parent's private members.
*   **`protected` members:** This is a new, important access modifier. A `protected` member is like `private`, but it **is accessible to derived classes**. This is the perfect choice for data that a parent class wants to share with its children, but not with the rest of the world.

### 5. Constructors and Inheritance
Constructors are **not** inherited. A derived class is responsible for its own initialization.

However, a derived class constructor **must** call a constructor of its base class to ensure the inherited parts of the object are initialized properly. We use the `base()` keyword to do this.

```csharp
public class Vehicle
{
    public string Make { get; set; }

    // Base class constructor
    public Vehicle(string make)
    {
        Make = make;
        Console.WriteLine("Vehicle constructor called!");
    }
}

public class Car : Vehicle
{
    public int NumberOfDoors { get; set; }

    // Derived class constructor
    // The ': base(make)' part calls the parent's constructor first.
    public Car(string make, int doors) : base(make)
    {
        NumberOfDoors = doors;
        Console.WriteLine("Car constructor called!");
    }
}

// When you do this:
Car myCar = new Car("Ford", 4);
// The output will be:
// Vehicle constructor called!
// Car constructor called!
```
The base class is always constructed *before* the derived class.

---
