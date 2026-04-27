# Week 1, Day 4: Organizing Code with Functions & Methods

## 📖 Lecture Notes (1 Hour)

### 1. Introduction: From Scripts to Programs
So far, our code has been a single, long list of instructions in one place. This works for small tasks, but as programs grow, it becomes messy, hard to read, and difficult to maintain. Today, we learn to organize our code into reusable blocks called **Methods** (also known as Functions in other languages).

The #1 reason to use methods is the **DRY Principle: Don't Repeat Yourself**.

### 2. The Anatomy of a Method
A method is a named block of code that performs a specific task. Let's break down its signature:

`public static int AddNumbers(int firstNumber, int secondNumber)`

*   **`public`**: An **Access Modifier**. It defines who can call this method. `public` means it can be called from anywhere. (We'll cover others like `private` later).
*   **`static`**: A keyword that means the method belongs to the class itself, not an instance of the class. For now, all our methods in Console apps will be `static`.
*   **`int`**: The **Return Type**. This specifies what kind of data the method will give back *after* it has finished its job.
*   **`AddNumbers`**: The **Method Name**. It should be descriptive and use PascalCase (starts with a capital letter).
*   **`(int firstNumber, int secondNumber)`**: The **Parameter List**. These are the inputs the method needs to do its job. Each parameter has a type and a name.

### 3. Return Types: Getting Data Back
*   **Methods that return a value:** These methods perform a calculation or find some data and use the `return` keyword to send the result back to whoever called them. The type of the returned value **must** match the declared return type.
    ```csharp
    public static double CalculateArea(double width, double height)
    {
        double area = width * height;
        return area; // Sends the calculated value back
    }
    // How to call it:
    double result = CalculateArea(10.5, 20.0); // result will be 210.0
    ```*   **`void` Methods:** The `void` keyword means the method **does not return any value**. Its job is simply to perform an action, like printing to the console or changing a UI element.
    ```csharp
    public static void PrintWelcomeMessage()
    {
        Console.WriteLine("=====================");
        Console.WriteLine(" Welcome to the App! ");
        Console.WriteLine("=====================");
        // No 'return' keyword is needed for a value.
    }
    // How to call it:
    PrintWelcomeMessage();
    ```

### 4. Parameters vs. Arguments
These two terms are often confused, but the distinction is important:
*   **Parameters:** The variables declared in the method's signature (`int firstNumber`). They are placeholders for the data the method expects.
*   **Arguments:** The actual values you provide when you **call** the method (`AddNumbers(5, 10)`). `5` and `10` are the arguments.

### 5. Variable Scope
A crucial concept: variables declared *inside* a method are **local** to that method. They only exist while the method is running. They cannot be seen or accessed by code outside of that method.

```csharp
public static void MyMethod()
{
    int localValue = 100; // This variable only exists inside MyMethod
}

public static void Main()
{
    MyMethod();
    // Trying to access localValue here would cause an error!
    // Console.WriteLine(localValue); // COMPILE ERROR!
}
```

### 6. The Art of Refactoring
**Refactoring** is the process of restructuring existing computer code—changing the factoring—without changing its external behavior.

A common refactoring task is to take a large, messy block of code (like a long `Button_Click` event handler) and extract logical parts into their own well-named methods. This makes the code cleaner, easier to understand, and reusable.

---
