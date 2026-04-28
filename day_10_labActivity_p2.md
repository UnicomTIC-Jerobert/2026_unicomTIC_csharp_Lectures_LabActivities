Excellent idea. Adding a second, distinct mini-project is a fantastic way to reinforce the OOP principles from a different perspective. The "Shapes" project is a classic and effective example for teaching these concepts. It provides very clear use cases for inheritance and polymorphism.

Here is the complete set of lab activities for the **Shapes Area and Perimeter Calculation Mini-Project**. This can be presented to the students as "Part 2" of the day's lab work, following the Zoo project.

***

## 💻 Lab Activities (Part 2) - OOP Mini-Project: Shapes Calculator

### **Objective**
To solidify the four pillars of OOP by designing and building a flexible system for calculating the geometric properties of various shapes. This project will reinforce the difference between an "is-a" relationship (inheritance) and a "can-do" capability (interfaces).

---

### **Part 1: The Console Logic Core (Activities 1-7)**

#### **Activity 1 (~30 mins): Core Abstractions - `Shape` and `I3DObject`**
*   **Concept:** Defining the highest-level contracts and base classes for the system.
*   **Task:** Create a new Console App `Day10_Shapes_Console`.
    1.  Create an `abstract` class file `Shape.cs`.
        *   Property: `public string Name { get; set; }`.
        *   Constructor: to set the `Name`.
        *   Abstract Methods: `public abstract double GetArea();` and `public abstract double GetPerimeter();`. These methods have no implementation as a generic shape doesn't have a defined formula.
    2.  Create an `interface` file `I3DObject.cs`.
        *   Method Signature: `double GetVolume();`. This defines the "can-calculate-volume" capability.

#### **Activity 2 (~35 mins): Concrete 2D Shapes - `Rectangle` & `Circle`**
*   **Concept:** Inheriting from an abstract class and providing concrete implementations for its abstract methods.
*   **Task:** In the same project:
    1.  Create a `Rectangle.cs` class that inherits from `Shape`.
        *   Add `Width` and `Height` properties.
        *   Create a constructor that accepts `width`, `height`, and `name`, and calls the `base(name)` constructor.
        *   `override` the `GetArea()` method to return `Width * Height`.
        *   `override` the `GetPerimeter()` method to return `2 * (Width + Height)`.
    2.  Create a `Circle.cs` class that inherits from `Shape`.
        *   Add a `Radius` property.
        *   Create its constructor.
        *   `override` `GetArea()` to return `Math.PI * Radius * Radius`.
        *   `override` `GetPerimeter()` to return `2 * Math.PI * Radius` (circumference).

#### **Activity 3 (~35 mins): A 3D-Capable Shape - `Sphere`**
*   **Concept:** A class that both inherits from a base class and implements an interface.
*   **Task:**
    1.  Create a `Sphere.cs` class that inherits from `Shape` **and** implements `I3DObject`.
    2.  Add a `Radius` property.
    3.  Create a constructor that calls the `base` constructor.
    4.  `override` `GetArea()` to return the *surface area* of the sphere: `4 * Math.PI * Radius * Radius`.
    5.  `override` `GetPerimeter()` to return `0` (a sphere doesn't have a traditional perimeter).
    6.  Implement the `GetVolume()` method from the `I3DObject` interface to return the sphere's volume: `(4.0 / 3.0) * Math.PI * Math.Pow(Radius, 3)`.

#### **Activity 4 (~30 mins): The `Canvas` Management Class**
*   **Concept:** Encapsulating the collection and the main logic that operates on it.
*   **Task:** Create a `Canvas.cs` class.
    1.  Add a `private List<Shape> shapes = new List<Shape>();` field.
    2.  Add a `public void AddShape(Shape shape)` method to add a shape to the list.
    3.  Add a `public void ClearCanvas()` method to clear the list.

#### **Activity 5 (~35 mins): Polymorphism for Area/Perimeter**
*   **Concept:** Using polymorphism to process a list of heterogeneous objects.
*   **Task:** In your `Canvas.cs` class:
    1.  Create a `public double CalculateTotalArea()` method. Inside, loop through the `shapes` list, sum the results of `shape.GetArea()` for each shape, and return the total.
    2.  Create a `public double CalculateTotalPerimeter()` method that does the same for the `GetPerimeter()` method.

#### **Activity 6 (~30 mins): Interface Logic for Volume**
*   **Concept:** Using interfaces to isolate and operate on objects with a specific capability.
*   **Task:** In your `Canvas.cs` class:
    1.  Create a `public double CalculateTotalVolumeOf3DObjects()` method.
    2.  Inside, loop through the `shapes` list.
    3.  For each shape, check if it implements the `I3DObject` interface using `if (shape is I3DObject)`.
    4.  If it does, cast it to the interface type (`I3DObject obj3d = (I3DObject)shape;`) and add the result of `obj3d.GetVolume()` to a running total.
    5.  Return the total volume.

#### **Activity 7 (~30 mins): Console Test Harness**
*   **Concept:** Creating a driver program to test the entire backend system.
*   **Task:** In `Program.cs`:
    1.  Create an instance of `Canvas`.
    2.  Add a `new Rectangle(5, 10, "R1")`, a `new Circle(7, "C1")`, and a `new Sphere(3, "S1")` to the canvas.
    3.  Call your calculation methods (`CalculateTotalArea`, `CalculateTotalPerimeter`, `CalculateTotalVolumeOf3DObjects`) and print the results to the console to verify everything works.

---

### **Part 2: The WPF Graphical User Interface (Activities 8-10)**

#### **Activity 8 (~45 mins): WPF UI Design**
*   **Concept:** Designing an adaptive UI that changes based on user selection.
*   **Task:** Create a new WPF App `Day10_Shapes_WPF`.
    1.  Design a UI with:
        *   A `ComboBox` named `ShapeTypeComboBox` with items: "Rectangle", "Circle", "Sphere".
        *   A `StackPanel` for Rectangle inputs (`WidthTextBox`, `HeightTextBox`).
        *   A `StackPanel` for Circle/Sphere inputs (`RadiusTextBox`). Hide one panel when the other is visible.
        *   An "Add Shape" `Button`.
        *   A `ListBox` named `CanvasListBox` to show the shapes on the canvas.
        *   Buttons: "Calculate Total Area", "Calculate Total Volume".
        *   A `TextBlock` named `ResultTextBlock` to display calculation results.

#### **Activity 9 (~45 mins): Wiring Up the UI Backend**
*   **Concept:** Connecting the UI controls to the C# object model.
*   **Task:** In `MainWindow.xaml.cs`:
    1.  Add all your shape-related class files to the project.
    2.  Create a private instance of `Canvas`: `private Canvas canvas = new Canvas();`.
    3.  Implement the `ComboBox`'s `SelectionChanged` event to show/hide the correct input `StackPanel`s.
    4.  Implement the "Add Shape" button's `Click` event. Use a `switch` on the `ComboBox` selection to `new` up the correct shape type using the data from the visible text boxes.
    5.  Add the new shape to your `canvas` object and also to the `CanvasListBox`. (Override `ToString()` in your shape classes for a nice display!)

#### **Activity 10 (~30 mins): Implementing the Action Buttons**
*   **Concept:** Triggering the polymorphic calculations from the UI.
*   **Task:**
    1.  Implement the `Click` event for the "Calculate Total Area" button. It should call `canvas.CalculateTotalArea()` and display the formatted result in the `ResultTextBlock`.
    2.  Implement the `Click` event for the "Calculate Total Volume" button. It should call `canvas.CalculateTotalVolumeOf3DObjects()` and display that result.
    3.  Finally, perform the **Git Submission** for this second project, adding it to the same commit as the Zoo project with an updated message like `"Day 10 Labs: Completed Zoo and Shapes OOP Mini-Projects"`.
