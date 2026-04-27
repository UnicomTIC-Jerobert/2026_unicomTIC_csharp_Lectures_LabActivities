## 💻 Lab Activities (6 Hours)

### **Objective**
To use `if`, `else if`, and `else` statements to control program flow. You will build a logic-driven console app and a state-changing WPF app that responds visually to user input based on conditions.

---

### **Task 1 (2 hrs): Console Age Checker**
This task focuses on using a chain of `if-else if-else` to categorize input.

1.  Create a new **Console App** project in your solution named `AgeCheckerApp`.
2.  Set it as the startup project.
3.  In `Program.cs`, write code to perform the following steps:
    *   Display a welcome message: `--- Age Categorizer ---`
    *   Prompt the user to enter their age: `Please enter your age:`
    *   Read the user's input using `Console.ReadLine()`.
    *   Convert the string input into an `int` variable. **Challenge:** What happens if the user types "abc"? For now, assume they enter a valid number. We'll handle errors later.
    *   Use an `if-else if-else` block to determine the user's category:
        *   If the age is less than 0, print `"Invalid age."`
        *   If the age is between 0 and 12 (inclusive), print `"You are a Child."`
        *   If the age is between 13 and 19, print `"You are a Teenager."`
        *   If the age is between 20 and 64, print `"You are an Adult."`
        *   If the age is 65 or older, print `"You are a Senior."`
4.  Run and test your application with different ages (e.g., `8`, `17`, `45`, `70`, `-5`) to ensure each condition works correctly.

**Example `Program.cs` structure:**
```csharp
Console.WriteLine("--- Age Categorizer ---");
Console.Write("Please enter your age: "); // Write keeps the cursor on the same line

string input = Console.ReadLine();
int age = int.Parse(input);

if (age < 0)
{
    // Your logic here...
}
else if (age <= 12)
{
    // Your logic here...
}
// ... and so on for the other conditions
```

✅ **Goal Check:** Your console application should correctly categorize any integer age the user provides.

---

### **Task 2 (2 hrs): WPF Login Form**
This task applies conditional logic to change the UI's content visually.

1.  Create a new **WPF Application** project named `LoginApp`.
2.  Set it as the startup project.
3.  In `MainWindow.xaml`, design a simple login form. You can use this XAML inside your `<Grid>`:
    ```xml
    <StackPanel HorizontalAlignment="Center" VerticalAlignment="Center" Width="300">
        <Label FontWeight="Bold">Username:</Label>
        <TextBox x:Name="UsernameTextBox" Margin="0,0,0,10"/>
        
        <Label FontWeight="Bold">Password:</Label>
        <PasswordBox x:Name="PasswordBox" Margin="0,0,0,20"/> 
        <!-- PasswordBox automatically hides characters -->
        
        <Button x:Name="LoginButton" Content="Login" Click="LoginButton_Click"/>
        
        <TextBlock x:Name="StatusTextBlock" Margin="0,20,0,0" TextAlignment="Center" FontSize="16" FontWeight="Bold"/>
    </StackPanel>
    ```
4.  Double-click the "Login" button in the designer to generate the `LoginButton_Click` event handler in `MainWindow.xaml.cs`.
5.  Inside the `LoginButton_Click` method, implement the logic:
    *   Get the text from `UsernameTextBox.Text`.
    *   Get the password from `PasswordBox.Password`.
    *   Use an `if` statement with a logical `&&` (AND) operator to check if the username is exactly `"admin"` **AND** the password is exactly `"1234"`.
    *   **If both are correct:**
        *   Set the `Text` of the `StatusTextBlock` to `"Login Successful!"`.
        *   Set the `Foreground` color of the `StatusTextBlock` to Green.
    *   **Else (if one or both are incorrect):**
        *   Set the `Text` of the `StatusTextBlock` to `"Invalid Username or Password"`.
        *   Set the `Foreground` color of the `StatusTextBlock` to Red.

**Example C# Code for the Click Event:**
```csharp
// You may need this using statement at the top of the file
using System.Windows.Media;

// ... inside your LoginButton_Click method
private void LoginButton_Click(object sender, RoutedEventArgs e)
{
    string username = UsernameTextBox.Text;
    string password = PasswordBox.Password;

    if (username == "admin" && password == "1234")
    {
        StatusTextBlock.Text = "Login Successful!";
        StatusTextBlock.Foreground = Brushes.Green; // A pre-defined color
    }
    else
    {
        StatusTextBlock.Text = "Invalid Username or Password";
        StatusTextBlock.Foreground = Brushes.Red;
    }
}
```

✅ **Goal Check:** Your WPF app should display a login form. Entering "admin" and "1234" should show a green success message. Any other input should show a red error message.

---

### **Task 3 (2 hrs): WPF UI State Change Challenge**
This is a more advanced challenge that builds directly on Task 2. We will manipulate UI properties beyond just text and color.

1.  Continue working in the `LoginApp` project.
2.  **The Goal:** When the user logs in successfully, we want to disable the login controls and show a "Logout" button. Clicking "Logout" should reset the form.
3.  **Modify the XAML:** Add a Logout button, but make it hidden by default.
    ```xml
    <!-- Add this button right after your LoginButton in the XAML -->
    <Button x:Name="LogoutButton" Content="Logout" Click="LogoutButton_Click" Visibility="Collapsed" Margin="0,10,0,0"/>
    ```
    *   `Visibility="Collapsed"` makes the button completely hidden and it doesn't take up any space.
4.  **Modify the C#:**
    *   In the `if (username == "admin" && password == "1234")` block, add code to:
        *   Disable the username and password boxes: `UsernameTextBox.IsEnabled = false;`
        *   Hide the login button: `LoginButton.Visibility = Visibility.Collapsed;`
        *   Show the logout button: `LogoutButton.Visibility = Visibility.Visible;`
    *   Now, generate the click event for the new Logout button (double-click it in the XAML or designer).
    *   Inside the `LogoutButton_Click` method, write the code to **reverse** all the changes:
        *   Clear the text boxes and status message.
        *   Re-enable the text boxes.
        *   Show the login button again.
        *   Hide the logout button again.

**Example C# for Logout:**
```csharp
private void LogoutButton_Click(object sender, RoutedEventArgs e)
{
    // Clear fields
    UsernameTextBox.Text = "";
    PasswordBox.Password = "";
    StatusTextBlock.Text = "";

    // Reset control states
    UsernameTextBox.IsEnabled = true;
    PasswordBox.IsEnabled = true;

    LoginButton.Visibility = Visibility.Visible;
    LogoutButton.Visibility = Visibility.Collapsed;
}
```

✅ **Goal Check:** A successful login should now visually transform the form. The login controls should become inactive, and a logout button should appear. Clicking logout should perfectly reset the form to its original state. This demonstrates controlling the UI's *state* with C# logic.
