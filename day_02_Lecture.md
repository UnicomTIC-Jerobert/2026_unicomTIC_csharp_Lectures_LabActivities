# Week 1, Day 2: Conditional Logic in Two Worlds

## 📖 Lecture Notes (1 Hour)

### 1. Introduction: Making Decisions in Code
So far, our programs have executed from top to bottom without any deviation. But powerful programs need to make decisions and behave differently based on the situation. This is called **Conditional Logic**.

Think about a simple login screen:
*   **IF** the password is correct, THEN show the user's dashboard.
*   **ELSE**, show an error message.

This "IF...THEN...ELSE" structure is the most fundamental concept in programming logic.

### 2. The `if` Statement: Your Primary Tool
The `if` statement checks if a condition is **true**. If it is, the code block inside `{}` is executed.

```csharp
int userAge = 20;

if (userAge >= 18)
{
    // This code will only run if userAge is 18 or greater.
    Console.WriteLine("Access granted. You are an adult.");
}
```

#### The `else` Statement: The Alternative Path
You can provide an alternative path with `else` for when the `if` condition is **false**.

```csharp
int userAge = 15;

if (userAge >= 18)
{
    Console.WriteLine("You are an adult.");
}
else
{
    // This code runs because the 'if' condition was false.
    Console.WriteLine("You are a minor.");
}
```

#### The `else if` Statement: Chaining Conditions
What if you have more than two possibilities? You can chain conditions together with `else if`. C# checks them in order and only executes the *first one* that is true.

```csharp
int score = 85;

if (score > 90)
{
    Console.WriteLine("Grade: A");
}
else if (score > 80) // This is checked only if the first 'if' was false.
{
    Console.WriteLine("Grade: B"); // This code will run!
}
else if (score > 70)
{
    Console.WriteLine("Grade: C");
}
else
{
    Console.WriteLine("Grade: F");
}
```

### 3. Essential Operators for Conditions
To build useful conditions, you need operators.

| Operator | Name | Example | Meaning |
| :--- | :--- | :--- | :--- |
| `==` | Equal to | `password == "1234"` | Is the password exactly "1234"? |
| `!=` | Not equal to | `userRole != "Admin"` | Is the user role *not* "Admin"? |
| `>` | Greater than | `age > 18` | Is the age strictly greater than 18? |
| `<` | Less than | `itemsInCart < 5` | Are there fewer than 5 items? |
| `>=` | Greater than or equal to | `score >= 50` | Is the score 50 or more? |
| `<=` | Less than or equal to | `price <= 100.00` | Is the price 100 or less? |
| `&&` | AND (Logical) | `user == "admin" && pass == "123"` | Are *both* conditions true? |
| `||` | OR (Logical) | `userRole == "Admin" || isOwner == true` | Is *at least one* of the conditions true? |

### 4. Application in Console vs. WPF
How we use conditional logic changes slightly based on our application type.

*   **In Console Apps:** We use `if` statements to control the **flow of text and logic**. We print different messages or call different functions.
*   **In WPF Apps:** We use `if` statements to control the **state of the UI**. We can change colors, show or hide elements, enable or disable buttons, and display different content. This is a very powerful concept.

### 5. The `switch` Statement (A Cleaner `if-else if`)
When you have many `else if` statements checking the *same variable* for different values, a `switch` statement is often cleaner and easier to read.

```csharp
// Using if-else if
string userCommand = "delete";
if (userCommand == "view") { /* ... */ }
else if (userCommand == "edit") { /* ... */ }
else if (userCommand == "delete") { /* This runs */ }
else { /* ... */ }

// Using switch (cleaner!)
switch (userCommand)
{
    case "view":
        // Code for viewing
        break; // The 'break' is essential!
    case "edit":
        // Code for editing
        break;
    case "delete":
        // Code for deleting - this block will run
        break;
    default:
        // This runs if no other case matches
        Console.WriteLine("Unknown command.");
        break;
}
```

