## 💻 Lab Activities (6 Hours)

### **Objective**
To define and implement interfaces, understand their role in polymorphism and decoupling, and use them to manage collections of otherwise unrelated objects.

### **Activity 1 (~30 mins): Defining an Interface**
*   **Concept:** Basic interface syntax.
*   **Console:** Create `Day9_Activity1_Interfaces`.
    1.  Create a new interface file named `ILoggable.cs`.
    2.  Inside, define the `ILoggable` interface with a single method signature: `void Log(string message);`. That's it!

### **Activity 2 (~35 mins): Implementing the Interface**
*   **Concept:** Fulfilling the interface contract in a class.
*   **Console:** In the same project:
    1.  Create a `ConsoleLogger.cs` class that implements `ILoggable`. The `Log` method should simply print the message to the console.
    2.  Create a `DatabaseLogger.cs` class that also implements `ILoggable`. Its `Log` method should print a simulated message like `"[DATABASE]: {message}"`.
    3.  In `Program.cs`, create an instance of both loggers and call their `Log` methods to test them.

### **Activity 3 (~35 mins): Polymorphism with Interfaces**
*   **Concept:** Using an interface type to hold different object instances.
*   **Console:** In `Program.cs`:
    1.  Create a `List<ILoggable>`.
    2.  Add your `ConsoleLogger` and `DatabaseLogger` objects to this list.
    3.  Create a separate method `public static void ProcessLogs(List<ILoggable> loggers)`. This method should loop through the list and call the `Log` method on each item with a standard message like "Processing item...".
    4.  Call `ProcessLogs` from `Main`, passing in your list.

### **Activity 4 (~40 mins): Multiple Interfaces**
*   **Concept:** A single class implementing more than one contract.
*   **Console:**
    1.  Create a new interface `IConfigurable` with a method `void Configure()`.
    2.  Modify your `DatabaseLogger` class so it implements *both* `ILoggable` and `IConfigurable`.
    3.  Provide an implementation for the `Configure()` method (e.g., print "Configuring database connection...").
    4.  In `Main`, prove that you can call both `Log()` and `Configure()` on your `DatabaseLogger` object.

### **Activity 5 (~40 mins): Interface vs. Inheritance**
*   **Concept:** Understanding when to use each tool.
*   **Console:** Create `Day9_Activity5_Hierarchy`.
    1.  Create an `IDrivable` interface with `Start()` and `Stop()` methods.
    2.  Create a `Vehicle` abstract class with a `NumberOfWheels` property.
    3.  Create a `Car` class that inherits from `Vehicle` **and** implements `IDrivable`.
    4.  Create a `Bicycle` class that inherits from `Vehicle` **and** implements `IDrivable`.
    5.  Create a `Robot` class that does *not* inherit from `Vehicle` but *does* implement `IDrivable`.
    6.  In `Main`, create a `List<IDrivable>` and add a `Car`, `Bicycle`, and `Robot` to it. Loop through and call `Start()` on all of them.

### **Activity 6 (~45 mins): WPF Media Player UI**
*   **Concept:** Designing a UI for a system that will be controlled via interfaces.
*   **WPF:** Create `Day9_Activity6_MediaPlayer`.
    1.  Design a UI with:
        *   A `ListBox` named `PlaylistListBox`.
        *   Buttons: "Play", "Pause", "Stop".
        *   A `TextBlock` named `StatusTextBlock` for messages.
        *   "Add" buttons: "Add Song", "Add Video".

### **Activity 7 (~45 mins): WPF Media Hierarchy**
*   **Concept:** Building the polymorphic backend using interfaces for the WPF app.
*   **WPF:**
    1.  Create an `IPlayable` interface with `Play()`, `Pause()`, and `Stop()` methods, and a `Title` string property.
    2.  Create a `Song` class that implements `IPlayable`. The `Play()` method should return a string like `"Playing song: {Title}"`. Override `ToString()` to return `"[SONG] {Title}"`.
    3.  Create a `Video` class that implements `IPlayable`. The `Play()` method should return `"Playing video: {Title}"`. Override `ToString()` to return `"[VIDEO] {Title}"`.

### **Activity 8 (~40 mins): Driving WPF with Interfaces**
*   **Concept:** Using interface polymorphism to control a UI.
*   **WPF:** In `MainWindow.xaml.cs`:
    1.  Create a `List<IPlayable>` named `playlist`.
    2.  The "Add Song" and "Add Video" buttons should create new objects, add them to the `playlist`, and also to the `PlaylistListBox`.
    3.  The "Play", "Pause", and "Stop" buttons should get the `SelectedItem` from the `ListBox`.
    4.  **Crucially:** Cast the selected item to `IPlayable`: `IPlayable selectedMedia = (IPlayable)PlaylistListBox.SelectedItem;`.
    5.  Check if `selectedMedia` is not null, then call the appropriate method (`Play()`, `Pause()`, etc.) and display the returned string in the `StatusTextBlock`.

### **Activity 9 (~10 mins): Git Submission**
*   **Task:** Stage, commit, and push your new projects to GitHub with the message: `"Day 9 Labs: Implemented Interfaces for Decoupling"`.

---
