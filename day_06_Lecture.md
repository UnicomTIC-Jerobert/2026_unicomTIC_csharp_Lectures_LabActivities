Yes, I will now generate the content for the next step: **Week 2, Day 1**.

I have validated your new structure and will adhere to it precisely:
1.  **Lectures:** The content will be approximately 1 hour long, explicitly covering concepts in both Console and WPF contexts.
2.  **Lab Activities:** There will be a minimum of 7 distinct tasks, split between Console and WPF, to provide comprehensive hands-on experience.
3.  **Quizzes:** The day will conclude with a minimum of 20 quiz questions to thoroughly test understanding.

Here is the curriculum for **Week 2, Day 1: Classes & Objects**.

***

# Week 2, Day 1: Introduction to Classes & Objects

## 📖 Lecture Notes (1 Hour)

### 1. Introduction: The Problem with Our Current Approach
Last week, we built a Vending Machine. Think about how we stored the data for each item:
`string itemName1; double itemPrice1; int itemStock1;`
`string itemName2; double itemPrice2; int itemStock2;`
...and so on.

This is messy! The data for a single item (its name, price, and stock) is scattered across three separate variables. If we want to add 50 items, this becomes a complete nightmare to manage. The **data (variables)** and the **behavior (methods)** are disconnected.

**Object-Oriented Programming (OOP)** solves this problem by allowing us to bundle related data and behavior together into a single, logical unit.

### 2. The Core Idea: Classes and Objects
This is the most important concept in modern programming.
*   **A Class is a Blueprint:** A class is a template or a blueprint for creating things. It defines a new **data type**. It describes the **properties** (data) and **methods** (behaviors) that things of its type will have. For example, a `Car` class would define that all cars have a `Color` property and a `StartEngine()` method.
*   **An Object is an Instance of a Class:** An object is the actual *thing* created from the blueprint. If `Car` is the class (the blueprint), then your specific red Ford Focus is an **object** (an instance). My blue Honda Civic is another, separate **object**. You can create many objects from a single class.

### 3. Defining a Class: The Blueprint Syntax
A class is a container for properties and methods.

```csharp
// This is the blueprint for a Student.
// It defines what EVERY student will have.
public class Student
{
    // 1. Properties (The Data)
    // These are the attributes or characteristics of a Student.
    // { get; set; } creates a modern C# property.
    public string Name { get; set; }
    public int StudentID { get; set; }
    public double GradePointAverage { get; set; }

    // 2. Methods (The Behavior)
    // These are the actions a Student can perform.
    // Notice it can use the properties of its own class.
    public void Introduce()
    {
        Console.WriteLine($"Hello, my name is {Name} and my ID is {StudentID}.");
    }
}
```

### 4. Creating an Object: Instantiation
To create an object from a class, we use the `new` keyword. This process is called **instantiation**.

```csharp
// Create a new object (an instance) of the Student class
Student student1 = new Student();

// Now we can set the properties of this specific instance
student1.Name = "Alice";
student1.StudentID = 101;
student1.GradePointAverage = 3.8;

// And we can call its methods
student1.Introduce(); // Output: Hello, my name is Alice and my ID is 101.

// We can create another, completely separate object
Student student2 = new Student();
student2.Name = "Bob";
student2.StudentID = 102;
```

### 5. Constructors: Initializing Objects
A **constructor** is a special method that runs automatically when you create a new object using the `new` keyword. Its job is to initialize the object's properties to a valid starting state. A constructor has the same name as the class and no return type.

```csharp
public class Book{
    public string Title { get; set; }
    public string Author { get; set; }

    // This is a constructor. It requires a title and author when creating a book.
    public Book(string title, string author)
    {
        Title = title;
        Author = author;
    }
}

// Now we MUST provide the data when creating the object:
Book myBook = new Book("The Hobbit", "J.R.R. Tolkien");
// myBook.Title is already set to "The Hobbit"
```

### 6. Application in Console vs. WPF
*   **Console:** In console apps, objects are the "business entities" or the "model" of our application. We create them, manipulate their data, call their methods, and print their information to the screen.
*   **WPF:** In WPF, objects are the **heart of the application's data**. This is a critical concept. We create an object (the **Model**) and then "bind" its properties to UI elements (the **View**). When a button is clicked, we don't manually change ten `TextBlock`s. Instead, we just load a different `Student` object, and the UI can update itself to reflect that object's state. This separates our logic from our presentation.

---
