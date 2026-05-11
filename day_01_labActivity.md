## 💻 Lab Activities (6 Hours)

### **Objective**
Gain hands-on experience with variable declaration, user input, type conversion, and basic arithmetic operations in both Console and WPF environments.

### **Activity 1 (1 hr): Foundational "Hello Worlds"**
*   **Concept:** The most basic program execution in both app models.
*   **Instructions:**
    1.  Create a new Solution in Visual Studio.
    2.  **Console Project:** Add a **Console App** named `Day1_Activity1_Console`. Write code to print `Hello from the Console!`.
    3.  **WPF Project:** Add a **WPF App** named `Day1_Activity1_WPF`. Add a `Button` that, when clicked, shows a `MessageBox` with the text `Hello from WPF!`.

### **Activity 1.1 (1.5 hrs): Interactive UI with Mouse Events**
*   **Concept:** Go beyond a simple click. Learn how to make a WPF application feel alive and responsive by handling different mouse events. We will make a single button react in multiple ways depending on how the user interacts with it.
*   **Goal:** You will modify the button from Activity 1 to:
    *   Change color and text when the mouse pointer hovers over it (`MouseEnter`).
    *   Revert to its original state when the mouse pointer leaves (`MouseLeave`).
    *   Change the window's title when it is double-clicked (`MouseDoubleClick`).
    *   Keep its original single-click functionality (`Click`).

#### **Instructions:**

1.  **Open Previous Project:** Continue working in your `Day1_Activity1_WPF` project. Open the `MainWindow.xaml` file.

2.  **Prepare the Button in XAML:** We need to give our button a name so we can easily reference it in our C# code. We'll also make it a bit bigger to make the effects more obvious.
    *   Find your `<Button ... />` tag in `MainWindow.xaml`.
    *   Modify it to look like this. The key additions are `Name`, `Height`, `Width`, and `FontSize`.

    ```xml
    <Button Name="InteractiveButton" 
            Content="Click Me!" 
            HorizontalAlignment="Center" 
            VerticalAlignment="Center" 
            Height="50" 
            Width="200"
            FontSize="16"
            Click="InteractiveButton_Click" />
    ```
    *   *Note:* Your `Click` event handler might have a different name if you let Visual Studio generate it. That's perfectly fine! Just make sure the `Name` property is added.

3.  **Add the `MouseEnter` Event:**
    *   Follow the steps in the **"Beginner's Guide"** below to add an event handler for the `MouseEnter` event.
    *   Visual Studio will automatically create a method called `InteractiveButton_MouseEnter` in your `MainWindow.xaml.cs` file.
    *   Inside this new method, add the following C# code. This code will change the button's background to a light green and update its text.

    ```csharp
    private void InteractiveButton_MouseEnter(object sender, System.Windows.Input.MouseEventArgs e)
    {
        // Change background color
        InteractiveButton.Background = Brushes.LightGreen;

        // Change the text content
        InteractiveButton.Content = "You are hovering over me!";
    }
    ```

4.  **Add the `MouseLeave` Event:**
    *   Now, do the same for the `MouseLeave` event. This will trigger when the mouse cursor moves off the button.
    *   Inside the new `InteractiveButton_MouseLeave` method, we will write code to change the button back to its original state.

    ```csharp
    private void InteractiveButton_MouseLeave(object sender, System.Windows.Input.MouseEventArgs e)
    {
        // Revert background color to the default button brush
        InteractiveButton.Background = SystemColors.ControlBrush; 
        
        // Revert the text content
        InteractiveButton.Content = "Click Me!";
    }
    ```
    *   **Run your application (press F5).** Test it! You should see the button change when you hover over it and change back when you move the mouse away.

5.  **Add the `MouseDoubleClick` Event:**
    *   Finally, let's add an event for a double-click. Use the same process to create a `MouseDoubleClick` event handler.
    *   Inside the `InteractiveButton_MouseDoubleClick` method, we'll add code to change the main window's title. The `this` keyword refers to the current class instance, which in this case is the `MainWindow`.

    ```csharp
    private void InteractiveButton_MouseDoubleClick(object sender, System.Windows.Input.MouseButtonEventArgs e)
    {
        // Change the title of the main window
        this.Title = "You Double-Clicked the Button!";
    }
    ```

6.  **Final Test:**
    *   Run the application again. Verify all behaviors:
        *   **Hover:** Button turns green and text changes.
        *   **Leave:** Button reverts to normal.
        *   **Single Click:** The `MessageBox` from Activity 1 still appears.
        *   **Double Click:** The window's title changes.

---

### **Beginner's Guide: How to Add Event Handlers in Visual Studio 2022**

In WPF, you connect a user action (like a click) to a piece of your C# code. The action is the **Event**, and the code that runs is the **Event Handler**. Here are two easy ways to do this.

#### **Method 1: The Properties Window (The Visual Way - Recommended for Beginners)**

This is the most straightforward method.

1.  **Open the XAML Designer:** Make sure you are viewing `MainWindow.xaml` in the designer view (you should see a visual representation of your window).

2.  **Select the Control:** Click on the `Button` in the designer or on its `<Button ...>` tag in the XAML code.

3.  **Open the Properties Window:** This window is usually on the bottom-right of Visual Studio. If you don't see it, go to the **View** menu and select **Properties Window**.

4.  **Switch to Events View:** At the top of the Properties Window, look for a small lightning bolt icon (⚡). Click it. This switches the list from properties (like `Width`, `Content`) to events (like `Click`, `MouseEnter`).

    

5.  **Find and Create the Event Handler:**
    *   Scroll through the list to find the event you want, for example, `MouseEnter`.
    *   **Double-click** in the empty text box next to the event name.

    

6.  **Magic!** Visual Studio automatically does two things:
    *   It creates a new method stub for you in the C# "code-behind" file (`MainWindow.xaml.cs`).
    *   It adds the necessary attribute to your XAML tag to link them, like `MouseEnter="InteractiveButton_MouseEnter"`.

#### **Method 2: The XAML Editor (The Code Way)**

This method is faster once you get used to it.

1.  **Click inside the XAML tag** for your control (e.g., `<Button ... >`).

2.  **Start typing the event name.** As you type `MouseEnter`, Visual Studio's IntelliSense will show you a list of matching events.

3.  **Select the event and press Tab.**

4.  IntelliSense will add `MouseEnter=""`. Inside the quotes, it will suggest **`<New Event Handler>`**.

    

5.  **Press Enter** to accept it. Just like the first method, Visual Studio will create the handler method in your C# file and name it for you.

#### **Key Concepts to Explain**

*   **The XAML-C# Connection:** Emphasize that the XAML file (`.xaml`) defines the *look and layout* of the UI and declares *which method to call* for an event. The C# file (`.xaml.cs`) defines the *behavior* and contains the actual logic for that method.
*   **The `sender` Argument:** Explain that `object sender` in the event handler (e.g., `InteractiveButton_MouseEnter(object sender, ...)` is a reference to the control that triggered the event. In our case, it's always the `InteractiveButton`. This is useful when multiple controls share the same event handler.
*   **The `e` (EventArgs) Argument:** Explain that the second argument (`MouseEventArgs e`, `MouseButtonEventArgs e`, etc.) contains extra information about the event. For example, `e.GetPosition(this)` could tell you the exact X/Y coordinates of the mouse when the event happened. For now, we don't need it, but it's very powerful.

---

### **Activity 2 (1 hr): User Profile Creator**
*   **Concept:** Handling `string` variables and user input.
*   **Instructions:**
    1.  **Console Project:** Create a new Console App `Day1_Activity2_Console`.
        *   Prompt the user for their First Name, Last Name, and Favorite Color.
        *   Store these inputs in three `string` variables.
        *   Print a formatted "bio" to the console, for example: `User Bio: John Doe's favorite color is Blue.`
    2.  **WPF Project:** Create a new WPF App `Day1_Activity2_WPF`.
        *   Design a UI with three `TextBox`es and a `Button`.
        *   When the button is clicked, read the text from all three boxes.
        *   Display the same formatted "bio" in a `TextBlock` control within the window.

### **Activity 3 (1 hr): Temperature Converter**
*   **Concept:** Handling `double` variables and applying a mathematical formula. This introduces decimal precision.
*   **Instructions:**
    1.  **Console Project:** Create `Day1_Activity3_Console`.
        *   Prompt the user to enter a temperature in Celsius.
        *   Read the input and use `double.Parse()` to convert it to a `double`.
        *   Calculate the temperature in Fahrenheit using the formula: `F = (C * 9 / 5) + 32`.
        *   Print the result clearly, e.g., `25°C is equal to 77°F.`
    2.  **WPF Project:** Create `Day1_Activity3_WPF`.
        *   Design a UI with a `TextBox` for Celsius input, a `Button` to "Convert", and a `TextBlock` for the result.
        *   On button click, parse the input, perform the calculation, and display the formatted result in the `TextBlock`.

### **Activity 4 (1 hr): Simple Calculator**
*   **Concept:** Reinforcing type conversion and handling multiple numeric inputs for basic arithmetic.
*   **Instructions:**
    1.  **Console Project:** Create `Day1_Activity4_Console`.
        *   Ask for two numbers from the user.
        *   Use `int.Parse()` to convert them.
        *   Calculate and print the Sum, Difference, Product, and Quotient.
        *   For the quotient, ensure you use `double` for an accurate decimal result.
    2.  **WPF Project:** Create `Day1_Activity4_WPF`.
        *   Design a UI with two `TextBox`es, four `Button`s ("+", "-", "*", "/"), and a `TextBlock` for the result.
        *   Implement the `Click` event for each button to perform the correct calculation and display the result.

### **Activity 5 (1 hr): Shape Area Calculator**
*   **Concept:** Applying geometric formulas and using the `Math` library.
*   **Instructions:**
    1.  **Console Project:** Create `Day1_Activity5_Console`.
        *   Ask the user for the width and height of a rectangle.
        *   Calculate and print the area (`Area = width * height`).
        *   Then, ask the user for the radius of a circle.
        *   Calculate and print the area (`Area = PI * radius * radius`). You can get PI from `Math.PI`.
    2.  **WPF Project:** Create `Day1_Activity5_WPF`.
        *   Design a UI with two sections (or use `TabControl` if you feel adventurous).
        *   **Section 1 (Rectangle):** Two `TextBox`es for width/height and a button to calculate the area.
        *   **Section 2 (Circle):** One `TextBox` for the radius and a button to calculate the area.
        *   Use a shared `TextBlock` to display the result of whichever calculation was last performed.

### **Activity 6 (1 hr): Git Repository Submission**
*   **Concept:** Finalizing and submitting the day's work using standard version control practices.
*   **Instructions:**
    1.  **Create `.gitignore`:** If you haven't already, create a `.gitignore` file in your solution's root directory. Populate it with the standard "Visual Studio" template to exclude temporary files.
    2.  **Commit All Work:** Open the Terminal in Visual Studio and run the following commands.
        ```bash
        # Stage all your new project files and the .gitignore file
        git add .
        
        # Commit the staged files with a comprehensive message for the day
        git commit -m "Day 1 Labs: Completed all 5 coding activities"
        ```
    3.  **Push to GitHub:**
        *   Create a new, empty repository on GitHub.com named `CSharp-Bootcamp-Work`.
        *   Connect your local repository to the remote one and push your code.
        ```bash
        git remote add origin YOUR_GITHUB_REPO_URL
        git branch -M main
        git push -u origin main
        ```
    4.  **Verification:** Refresh your GitHub page. Confirm that all 10 project folders (5 console, 5 WPF) are present.

---

