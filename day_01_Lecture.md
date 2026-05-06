# Week 1, Day 1: The Two "Hello Worlds" - Logic vs. Presentation

## 📖 Lecture Notes (1 Hour)

### 1. Welcome to .NET!
Welcome to the world of C# and .NET!

*   **.NET is a Framework:** Think of it as a giant, pre-built toolkit for creating software. It provides a huge library of code that handles common tasks (like reading files, connecting to the internet, or drawing things on screen) so we don't have to write everything from scratch.
*   **C# is the Language:** C# (pronounced "C Sharp") is the modern, powerful programming language we will use to tell the .NET framework what to do.
*   **Cross-Platform:** With .NET, the C# code you write can run on Windows, macOS, and Linux. For today, our WPF apps will be Windows-only, but the C# logic itself is portable.

### 2. Our First Two App Models: Console vs. WPF

Today, we will build two different kinds of apps to understand a core concept: **Logic vs. Presentation**. C# is the language for logic, and we can apply that logic to different presentation layers.

| Feature | Console Application | WPF Application (Windows Presentation Foundation) |
| :--- | :--- | :--- |
| **Interface** | Text-based (in a terminal or command prompt) | Graphical (buttons, text boxes, images, etc.) |
| **User Input** | Typing commands (`Console.ReadLine()`) | Clicking buttons, typing in text boxes, etc. |
| **Primary Use** | Learning pure C# logic, backend services, automation scripts | Rich desktop applications for Windows |
| **Analogy** | A phone call (pure information) | A video call (information with a visual interface) |

### 3. Why We Learn WPF, and Where It Fits
WPF is useful because it lets us turn C# logic into a real Windows desktop application. Instead of only typing and reading text in a console, students can build screens with buttons, text boxes, labels, lists, and tables. This helps us learn an important idea in software development: the same business logic can be used behind different user interfaces.

WPF also introduces important professional programming ideas:
*   **Event-driven programming:** Code runs when the user clicks a button, types text, or selects an item.
*   **Separation of UI and logic:** XAML describes the screen, while C# handles the behavior.
*   **Data binding:** UI controls can display data from C# objects.
*   **Desktop application structure:** Students learn how a real Windows application is organized.

However, WPF also has limitations:
*   **Windows-only:** WPF applications run on Windows desktop, not directly on macOS, Linux, Android, iOS, or the web.
*   **Not for web applications:** Websites and web APIs are usually built with technologies like ASP.NET Core, Blazor, JavaScript, HTML, and CSS.
*   **Not the newest UI framework:** Modern .NET also has options like .NET MAUI, WinUI, Blazor, and Avalonia.
*   **Can feel complex at first:** XAML, events, layouts, and data binding add extra concepts on top of basic C#.

In this course, we use WPF as a learning tool for desktop UI programming. The most important part is still the C# logic. The programming concepts you learn here will also help you later with web apps, APIs, mobile apps, games, and other .NET technologies.

### 4. Core C# Syntax: The Rules of the Language

Every language has grammar, and C# is no different. Here are the first rules you need to know.

```csharp
// This is a single-line comment. The computer ignores it.

/*
  This is a
  multi-line comment.
*/

// Every C# application starts running in a method called "Main".
// A "method" is a block of code that performs a task.
public static void Main(string[] args)
{
    // A statement is a single instruction. It MUST end with a semicolon (;).
    Console.WriteLine("This is a statement.");
    
    // Statements are executed in order, from top to bottom.
    Console.WriteLine("This is the second statement.");

} // The curly braces {} define the start and end of a code block.
```

### 5. Variables: Storing Information
A variable is a container for storing data. You must declare what **type** of data a variable will hold.

| Data Type | Purpose | Example |
| :--- | :--- | :--- |
| `string` | For text | `string name = "Alice";` |
| `int` | For whole numbers | `int age = 30;` |
| `double` | For numbers with decimals | `double temperature = 98.6;` |
| `bool` | For true/false values | `bool isLoggedIn = true;` |

**Example:**
```csharp
string userName = "Admin";
int userScore = 100;
bool isLevelComplete = false;

// You can change the value later
userScore = 150; 
```

### 6. Getting User Input: The Two Worlds

How we get input from a user depends entirely on our app model.

*   **Console:** We use `Console.ReadLine()`. This command pauses the program, waits for the user to type something and press Enter, and then returns what they typed as a `string`.
    ```csharp
    Console.WriteLine("Please enter your name:");
    string name = Console.ReadLine(); 
    ```
*   **WPF:** We use UI controls. A user types into a `TextBox` control. In our C# code, we access the `.Text` property of that control to get the input.
    ```csharp
    // In our C# event handler for a button click:
    string name = NameTextBox.Text; // Assumes our TextBox is named "NameTextBox"
    ```

### 7. Introduction to XAML: The Blueprint for Your UI
In WPF, we don't use C# to describe *what the UI looks like*. We use a special language called **XAML** (eXtensible Application Markup Language).

Think of XAML as the architectural blueprint for your window. C# is the construction crew that brings the blueprint to life and makes it interactive.

**Example XAML for a simple button:**
```xml
<Window ... >
    <Grid>
        <!-- This XAML code creates a button on the screen -->
        <Button Content="Click Me" Width="100" Height="30" />
    </Grid>
</Window>
```
