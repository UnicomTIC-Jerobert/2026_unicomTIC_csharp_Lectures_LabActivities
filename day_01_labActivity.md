## 💻 Lab Activities (6 Hours)

### **Objective**
Gain hands-on experience with variable declaration, user input, type conversion, and basic arithmetic operations in both Console and WPF environments.

### **Activity 1 (1 hr): Foundational "Hello Worlds"**
*   **Concept:** The most basic program execution in both app models.
*   **Instructions:**
    1.  Create a new Solution in Visual Studio.
    2.  **Console Project:** Add a **Console App** named `Day1_Activity1_Console`. Write code to print `Hello from the Console!`.
    3.  **WPF Project:** Add a **WPF App** named `Day1_Activity1_WPF`. Add a `Button` that, when clicked, shows a `MessageBox` with the text `Hello from WPF!`.

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
---

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
    3. **Two-Way Temperature Converter**

        *   **Concept:**
              This activity builds on the previous one by creating a more dynamic user experience. You will handle real-time text changes, manage user input safely, and learn how to solve a common problem where two events can trigger each other in an infinite loop.
        *   **Instructions:**
            1.  **WPF Project:** Create a new WPF project named `Day1_Activity3_WPF`.
            2.  **Design the UI:**
                *   Add two `TextBox` controls: one for Celsius and one for Fahrenheit.
                *   Add corresponding `Label` controls so the user knows which is which.
            3.  **Implement Two-Way Logic:**
                *   When the user types a valid number into the **Celsius** box, the **Fahrenheit** box should update instantly with the converted value.
                *   When the user types a valid number into the **Fahrenheit** box, the **Celsius** box should update instantly with the converted value.
                *   If the user enters invalid text (like "abc") or clears a `TextBox`, the other `TextBox` should also be cleared.

### **WPF Implementation**

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
    
---

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

