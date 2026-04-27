Of course. Let's structure Day 3 with the same intensive and engaging format. This day is crucial as it introduces loops, a fundamental concept for handling repetitive tasks and processing data collections.

Here is the complete curriculum for Week 1, Day 3, with detailed lecture notes, 10 lab activities (5 coding topics split between Console/WPF, plus submission), and a comprehensive 20-question quiz.

***

# Week 1, Day 3: Repetition with Loops

## 📖 Lecture Notes (1 Hour)

### 1. Introduction: Why Do We Need Loops?
Imagine you need to print "Hello" five times. You could write `Console.WriteLine("Hello");` five times. But what if you need to do it 500 times? Or a million times? Repeating code is inefficient and error-prone.

Loops are a fundamental programming construct that allows us to execute a block of code **repeatedly** as long as a certain condition is met. This follows the **DRY (Don't Repeat Yourself)** principle of software development.

### 2. The `for` Loop: When You Know the Number of Repetitions
The `for` loop is perfect when you know exactly how many times you want to repeat an action. It has a very specific structure with three parts inside the parentheses, separated by semicolons.

**Structure:** `for (initializer; condition; iterator)`

```csharp
// This loop will run exactly 10 times.
for (int i = 1; i <= 10; i++)
{
    // i is our "loop counter" variable.
    // It starts at 1, the loop continues as long as i <= 10,
    // and after each run, i increases by 1 (i++).
    Console.WriteLine($"Current number is: {i}");
}
```
1.  **Initializer (`int i = 1`):** Runs only **once** at the very beginning. It declares and sets up our counter variable.
2.  **Condition (`i <= 10`):** Is checked **before** every loop run. If it's true, the code block executes. If it's false, the loop terminates.
3.  **Iterator (`i++`):** Runs **after** every loop run. It updates the counter variable, moving us closer to the end condition.

### 3. The `while` Loop: When the Condition is Uncertain
The `while` loop is used when you want to loop as long as a condition is true, but you don't necessarily know how many times it will run. The condition is checked **before** the code block is executed.

```csharp
string passwordAttempt = "";
while (passwordAttempt != "secret")
{
    Console.WriteLine("Enter the password:");
    passwordAttempt = Console.ReadLine();
}
Console.WriteLine("Access Granted!");
```
This loop could run once, or a thousand times, depending on the user's input. If the condition is false to begin with, the loop will never run at all.

### 4. The `do-while` Loop: Guaranteed to Run at Least Once
The `do-while` loop is a variation of the `while` loop. The key difference is that the condition is checked **after** the code block is executed. This means a `do-while` loop is **guaranteed to run at least once**. This is perfect for things like interactive menus.

```csharp
int choice;
do
{
    Console.WriteLine("1. Start Game");
    Console.WriteLine("2. Load Game");
    Console.WriteLine("3. Exit");
    choice = int.Parse(Console.ReadLine());
    // ... logic to handle choice ...
} while (choice != 3); // The loop continues until the user chooses to exit.
```

### 5. Loop Control Statements
Sometimes you need to change a loop's flow from the inside.

*   **`break;`**: Immediately **terminates** the entire loop, regardless of the loop's condition.
*   **`continue;`**: Immediately **skips the rest of the current iteration** and jumps to the start of the next one.

```csharp
for (int i = 1; i <= 10; i++)
{
    if (i % 2 != 0) // If the number is odd...
    {
        continue; // ...skip this iteration.
    }
    if (i > 8)
    {
        break; // If i is greater than 8, exit the loop completely.
    }
    Console.WriteLine(i); // This will only print 2, 4, 6, 8
}
```

---
