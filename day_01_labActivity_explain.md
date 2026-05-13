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

### ** Activity 3 : (part3 : WPF Implementation)**

This consists of two parts: the XAML for the layout and the C# "code-behind" for the logic.

#### **1. The XAML (`MainWindow.xaml`)**

This XAML uses a `Grid` to create a clean, aligned layout for our labels and text boxes.

```xml
<Window x:Class="Day1_Activity3_WPF.MainWindow"
        xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
        xmlns:d="http://schemas.microsoft.com/expression/blend/2008"
        xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"
        xmlns:local="clr-namespace:Day1_Activity3_WPF"
        mc:Ignorable="d"
        Title="Two-Way Temperature Converter" Height="200" Width="400">
    <Grid Margin="20">
        <Grid.ColumnDefinitions>
            <ColumnDefinition Width="Auto"/>
            <ColumnDefinition Width="*"/>
        </Grid.ColumnDefinitions>
        <Grid.RowDefinitions>
            <RowDefinition Height="Auto"/>
            <RowDefinition Height="Auto"/>
        </Grid.RowDefinitions>

        <!-- Celsius Row -->
        <Label Content="Celsius (°C):" 
               Grid.Row="0" Grid.Column="0" 
               VerticalAlignment="Center" 
               FontSize="16" Margin="0,0,10,0"/>
        
        <TextBox x:Name="celsiusTextBox" 
                 Grid.Row="0" Grid.Column="1" 
                 FontSize="16" VerticalContentAlignment="Center" Margin="5"
                 TextChanged="CelsiusTextBox_TextChanged"/>

        <!-- Fahrenheit Row -->
        <Label Content="Fahrenheit (°F):" 
               Grid.Row="1" Grid.Column="0" 
               VerticalAlignment="Center" 
               FontSize="16" Margin="0,0,10,0"/>
        
        <TextBox x:Name="fahrenheitTextBox" 
                 Grid.Row="1" Grid.Column="1" 
                 FontSize="16" VerticalContentAlignment="Center" Margin="5"
                 TextChanged="FahrenheitTextBox_TextChanged"/>
    </Grid>
</Window>
```

**What we did here:**
*   We created a two-row, two-column grid for alignment.
*   Named our text boxes `celsiusTextBox` and `fahrenheitTextBox`.
*   Crucially, we added the `TextChanged` event to both text boxes. You can use the "Properties -> Events (⚡)" window to generate these, or just type them in the XAML as shown above and let Visual Studio create the methods for you.

#### **2. The C# Code-Behind (`MainWindow.xaml.cs`)**

This is where the real magic happens. We need to handle the logic and, most importantly, prevent the infinite loop.

```csharp
using System.Windows;
using System.Windows.Controls;

namespace Day1_Activity3_WPF
{
    public partial class MainWindow : Window
    {
        // This flag is CRITICAL to prevent an infinite loop.
        private bool isUpdating = false;

        public MainWindow()
        {
            InitializeComponent();
        }

        private void CelsiusTextBox_TextChanged(object sender, TextChangedEventArgs e)
        {
            // If this change was caused by our own code, do nothing.
            if (isUpdating) return;

            // Use TryParse for safe conversion. It won't crash on bad input.
            if (double.TryParse(celsiusTextBox.Text, out double celsiusValue))
            {
                // Formula: F = (C * 9 / 5) + 32
                double fahrenheitValue = (celsiusValue * 9 / 5.0) + 32;

                // Set the flag to true before we programmatically change the other TextBox
                isUpdating = true;
                // Update the Fahrenheit TextBox, formatted to two decimal places
                fahrenheitTextBox.Text = fahrenheitValue.ToString("F2");
                // Unset the flag
                isUpdating = false;
            }
            else
            {
                // If input is not a valid number (e.g., empty or "abc"), clear the other box.
                fahrenheitTextBox.Text = string.Empty;
            }
        }

        private void FahrenheitTextBox_TextChanged(object sender, TextChangedEventArgs e)
        {
            // If this change was caused by our own code, do nothing.
            if (isUpdating) return;
            
            if (double.TryParse(fahrenheitTextBox.Text, out double fahrenheitValue))
            {
                // Formula: C = (F - 32) * 5 / 9
                double celsiusValue = (fahrenheitValue - 32) * 5 / 9.0;
                
                // Set the flag before updating the other TextBox
                isUpdating = true;
                // Update the Celsius TextBox
                celsiusTextBox.Text = celsiusValue.ToString("F2");
                // Unset the flag
                isUpdating = false;
            }
            else
            {
                // If input is not valid, clear the other box.
                celsiusTextBox.Text = string.Empty;
            }
        }
    }
}
```

### **Detailed Implementation Breakdown for Beginners**

#### 1. The Infinite Loop Problem (The Most Important Concept Here!)

Imagine what would happen without the `isUpdating` flag:
1.  You type `25` into the Celsius box.
2.  The `CelsiusTextBox_TextChanged` event fires.
3.  Your code calculates `77.00` and sets `fahrenheitTextBox.Text = "77.00"`.
4.  Because you *changed the text* in the Fahrenheit box, the `FahrenheitTextBox_TextChanged` event now fires!
5.  That code calculates `25.00` and sets `celsiusTextBox.Text = "25.00"`.
6.  Because you *changed the text* in the Celsius box, the `CelsiusTextBox_TextChanged` event fires again!
7.  This creates an infinite loop that can freeze or crash your application.

#### 2. The `isUpdating` Flag Solution

The `private bool isUpdating = false;` variable acts as a "gatekeeper" or a "Do Not Disturb" sign.
*   **Normally**, it's `false`.
*   **Before** our code is about to programmatically change a textbox, we set `isUpdating = true;`. This is like putting up the "Do Not Disturb" sign.
*   The *first line* in each event handler is `if (isUpdating) return;`. This checks the sign. If it's up, the method immediately stops and does nothing, breaking the loop.
*   **After** our code has finished its update, we set `isUpdating = false;` to take the sign down, allowing user-initiated changes to work again.

#### 3. Safe Input with `double.TryParse()`

In the previous version, we might have used `double.Parse()`. This is dangerous because if the user types `"abc"` or an empty string, `double.Parse()` will crash the application.

`double.TryParse()` is the safe way:
*   It tries to convert the text to a `double`.
*   If it succeeds, it returns `true` and puts the result into the variable you provide with the `out` keyword (e.g., `out double celsiusValue`).
*   If it fails, it returns `false` and doesn't crash.
*   This allows us to use it in an `if` statement to handle both valid numbers and invalid input gracefully.

#### 4. Formatting the Output

The line `fahrenheitValue.ToString("F2")` is a nice touch. It formats the number as a string with exactly two decimal places (`F2`), making the output look clean and consistent.   
    
