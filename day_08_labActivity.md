## 💻 Lab Activities (6 Hours)

### **Objective**
To understand and implement polymorphism using `virtual` and `override`. To build flexible applications that can handle collections of related but different objects seamlessly.

### **Activity 1 (~35 mins): The Base `Shape` Class**
*   **Concept:** Defining a base class with `virtual` members.
*   **Console:** Create a new Console App `Day8_Activity1_Shapes`.
    1.  Create a `Shape.cs` class file.
    2.  Give it a `public string Name { get; set; }` property.
    3.  Add a `public virtual double GetArea()` method. This method should simply `return 0;`. This acts as a default implementation.
    4.  Add a constructor that accepts a `name`.

### **Activity 2 (~40 mins): Derived `Rectangle` and `Circle` Classes**
*   **Concept:** Overriding base class methods to provide specific implementations.
*   **Console:** In the same project:
    1.  Create a `Rectangle.cs` class that inherits from `Shape`. Add `Width` and `Height` properties. Create a constructor that takes `width`, `height`, and a `name`, and calls the `base` constructor.
    2.  `override` the `GetArea()` method to return the correct area (`Width * Height`).
    3.  Create a `Circle.cs` class that inherits from `Shape`. Add a `Radius` property. Create its constructor.
    4.  `override` the `GetArea()` method to return the correct area (`Math.PI * Radius * Radius`).

### **Activity 3 (~40 mins): Polymorphism in a List**
*   **Concept:** The primary demonstration of polymorphism's power.
*   **Console:** In your `Program.cs` `Main` method:
    1.  Create a `List<Shape>`.
    2.  Add a `new Rectangle(5, 10, "My Rectangle")` to the list.
    3.  Add a `new Circle(7, "My Circle")` to the list.
    4.  Add another `new Rectangle(3, 4, "Small Rectangle")` to the list.
    5.  Use a `foreach` loop to iterate through your `List<Shape>`. Inside the loop, for each `shape` object, print its `Name` and the result of calling `shape.GetArea()`.
    6.  Observe how the correct `GetArea()` method is called for each object, even though the loop variable is of type `Shape`.

### **Activity 4 (~30 mins): Overriding `ToString()`**
*   **Concept:** Providing a custom, readable string representation for your objects.
*   **Console:**
    1.  Go to your `Rectangle.cs` file. Add `public override string ToString()`. Make it return a descriptive string like `"[Rectangle] Name: {Name}, Width: {Width}, Height: {Height}"`.
    2.  Do the same for your `Circle.cs` file.
    3.  Go back to your `Program.cs` loop. Instead of manually printing the details, just call `Console.WriteLine(shape);`. C# will automatically use your overridden `ToString()` method.

### **Activity 5 (~45 mins): WPF Notification System UI**
*   **Concept:** Designing a UI to interact with a polymorphic system.
*   **WPF:** Create `Day8_Activity5_Notifications`.
    1.  Design a UI with:
        *   A "Send" `Button` for each notification type: "Send Email", "Send SMS".
        *   A `ListBox` named `NotificationHistoryListBox` that will show a history of all sent notifications.
        *   A `TextBlock` named `StatusTextBlock` to show the result of the last action.

### **Activity 6 (~45 mins): The Notification Class Hierarchy**
*   **Concept:** Building the polymorphic backend for the WPF app.
*   **WPF:**
    1.  Create a `Notification.cs` base class. It should have a `public virtual string Send()` method that returns `"Generic notification sent."`.
    2.  Create an `EmailNotification.cs` class that inherits from `Notification`. Add a `RecipientEmail` property. `override` the `Send()` method to return `$"Email sent to {RecipientEmail}"`. Also, `override` `ToString()` to return `"[EMAIL] To: {RecipientEmail}"`.
    3.  Create an `SmsNotification.cs` class that inherits from `Notification`. Add a `PhoneNumber` property. `override` both the `Send()` and `ToString()` methods similarly.

### **Activity 7 (~45 mins): Driving the WPF App with Polymorphism**
*   **Concept:** Using a single collection to manage different UI-related object types.
*   **WPF:** In `MainWindow.xaml.cs`:
    1.  Create a `List<Notification>` as a member variable to store the history: `private List<Notification> notificationHistory = new List<Notification>();`.
    2.  In the "Send Email" `Button_Click` event:
        *   Create a `new EmailNotification { RecipientEmail = "student@example.com" }`.
        *   Call the object's `Send()` method and display the result in `StatusTextBlock`.
        *   Add the object to your `notificationHistory` list.
        *   Call a helper method `UpdateHistoryListBox()` (see below).
    3.  Do the same for the "Send SMS" button.
    4.  Create the helper method `private void UpdateHistoryListBox()`. This method should clear the `ListBox` and then loop through your `notificationHistory` list, adding each `notification` object to the `ListBox.Items`. Because we overrode `ToString()`, the `ListBox` will display them correctly.

### **Activity 8 (~15 mins): Git Submission**
*   **Task:** Stage, commit, and push your new projects to GitHub with the message: `"Day 8 Labs: Implemented Polymorphism with Virtual and Override"`.

---
