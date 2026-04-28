
## 💻 Lab Activities (6 Hours)

### **Objective**
To define custom classes, create objects (instances) from them, and use those objects to manage data and behavior in both Console and WPF applications.

### **Activity 1 (~40 mins): Defining the `Book` Class**
*   **Concept:** Basic class and property definition.
*   **Console:** Create a new Console App `Day6_Activity1_Console`.
    1.  In the Solution Explorer, right-click the project and select **Add > Class...**.
    2.  Name the new file `Book.cs` and click Add.
    3.  Inside the new file, define the `Book` class with the following public properties:
        *   `Title` (string)
        *   `Author` (string)
        *   `ISBN` (string)
        *   `NumberOfPages` (int)
*   **Task:** You will not write any code in `Program.cs` for this activity. The goal is simply to create the class file and define its properties correctly.

### **Activity 2 (~40 mins): Instantiation and Usage**
*   **Concept:** Creating and manipulating objects from a class.
*   **Console:** Continue in `Day6_Activity1_Console`.
    1.  In your `Main` method in `Program.cs`, create two different `Book` objects.
    2.  For the first book object, set its properties to your favorite book's details.
    3.  For the second book object, set its properties to another book's details.
    4.  Write `Console.WriteLine` statements to print out the details of both books in a clean, formatted way.

### **Activity 3 (~40 mins): Adding Behavior with Methods**
*   **Concept:** Defining methods inside a class that operate on the class's own data.
*   **Console:** Go back to your `Book.cs` file.
    1.  Add a `public void DisplayInfo()` method to the `Book` class.
    2.  This method should contain the `Console.WriteLine` logic to print the book's Title, Author, and ISBN.
    3.  Now, go back to your `Main` method in `Program.cs`. Instead of using `Console.WriteLine` there, simply call `book1.DisplayInfo();` and `book2.DisplayInfo();`. This cleans up your `Main` method significantly.

### **Activity 4 (~40 mins): Using Constructors**
*   **Concept:** Forcing objects to be created in a valid state.
*   **Console:** In your `Book.cs` file:
    1.  Create a public constructor for the `Book` class that accepts `title` and `author` as parameters. Inside the constructor, assign these parameter values to the `Title` and `Author` properties.
    2.  Go back to `Program.cs`. Your old `new Book();` code will now show an error!
    3.  Modify your object creation code to use the new constructor, passing the title and author directly, like this: `Book book1 = new Book("Your Book Title", "The Author");`.

### **Activity 5 (~45 mins): WPF UI for a Book Profile**
*   **Concept:** Designing a graphical front-end to display object data.
*   **WPF:** Create a new WPF App `Day6_Activity5_WPF`.
    1.  Design a user interface that can display all the information for a single book. It should include:
        *   Labels like "Title:", "Author:", "ISBN:", "Pages:".
        *   Adjacent `TextBlock` controls (e.g., `TitleTextBlock`, `AuthorTextBlock`, etc.) where the data will be displayed. Give them all `x:Name`.
        *   Two buttons at the bottom: "Load Book 1" and "Load Book 2".

### **Activity 6 (~45 mins): Linking the `Book` Class to WPF**
*   **Concept:** Using a custom class within a WPF application's code-behind.
*   **WPF:** Continue in `Day6_Activity5_WPF`.
    1.  Add the `Book.cs` class file you created earlier to this WPF project. (You can right-click the project > Add > Existing Item... and browse to the file).
    2.  In `MainWindow.xaml.cs`, at the top of the `MainWindow` class (but inside it), declare two `Book` objects as member variables:
        ```csharp
        public partial class MainWindow : Window
        {
            private Book book1;
            private Book book2;
            
            public MainWindow() // This is the constructor for the window
            {
                // ...
            }
        }
        ```
    3.  Inside the `MainWindow()` constructor, *initialize* these two book objects with data using your constructor from Activity 4.

### **Activity 7 (~45 mins): Driving the UI with Objects**
*   **Concept:** The core of WPF data handling: updating the UI based on an object's state.
*   **WPF:** Continue in `Day6_Activity5_WPF`.
    1.  Create a `Click` event for your "Load Book 1" button. Inside this event, write the code to take the data *from* your `book1` object and place it *into* the corresponding `TextBlock` controls.
        ```csharp
        // Example for one property
        TitleTextBlock.Text = book1.Title;
        // ... do this for all properties
        ```
    2.  Create a `Click` event for your "Load Book 2" button and do the same, but using the `book2` object's data.
    3.  Run the application. When you click each button, the UI should update to show the details of the corresponding book object.

### **Activity 8 (~10 mins): Git Submission**
*   **Concept:** Commit your first Object-Oriented project.
*   **Task:** Stage, commit, and push your 3 new projects to your GitHub repository with the commit message: `"Day 6 Labs: Introduction to Classes and Objects"`.

---
