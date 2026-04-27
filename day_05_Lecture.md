Of course. A mini-project day is the perfect way to conclude the first week. It solidifies all the foundational concepts by having students apply them to a single, coherent application. This structure transforms the 10 activities into a 10-step guided project, which is an excellent pedagogical approach.

Here is the complete curriculum for Week 1, Day 5, designed to be a capstone for the week's learning.

***

# Week 1, Day 5: Mini-Project Consolidation

## 📖 Lecture Notes (1 Hour)

### 1. Weekly Review: The Core Building Blocks
Let's quickly recap what we've learned this week. These are the absolute fundamentals of programming in C#.
*   **Day 1: Variables & I/O:** We learned how to store data (`int`, `string`, `double`, `bool`) and how to interact with the user (reading input and displaying output) in both Console and WPF.
*   **Day 2: Conditional Logic:** We gave our programs a brain using `if`, `else if`, and `else` statements, combined with logical operators (`&&`, `||`) to make decisions.
*   **Day 3: Loops:** We learned how to perform repetitive tasks efficiently using `for` loops (for known counts), `while` loops (for uncertain conditions), and `do-while` loops (for menus).
*   **Day 4: Methods:** We learned how to organize our code into clean, reusable, and readable blocks. This is the key to building larger, maintainable applications.

### 2. From Blocks to Buildings: The Project Mindset
Today, we stop learning individual new concepts. Instead, we will act like real developers and **integrate** all these building blocks to create a complete, functional application. This requires a shift in thinking:
*   **Top-Down Design:** We'll start with the big picture ("What should the app do?") and then break it down into smaller, manageable problems.
*   **Problem Decomposition:** Each small problem will be solved by a dedicated method. For example, instead of one giant block of code, we'll have methods like `DisplayMenu()`, `GetUserChoice()`, `ProcessTransaction()`, etc.
*   **The Main Loop:** The core of our application will be a central loop that orchestrates calls to all our helper methods.

### 3. Introducing Today's Project: The Simple Vending Machine
We will build a simulated vending machine. Think about what it needs to do:
1.  Show a list of available items and their prices.
2.  Run continuously until the user decides to exit.
3.  Allow the user to select an item.
4.  Ask the user to insert money.
5.  Check if the item is in stock.
6.  Check if the user inserted enough money.
7.  If successful, dispense the "item" and calculate the correct change.
8.  If unsuccessful, provide a clear error message.

This simple idea forces us to use every single concept we've learned this week. We will build the complete logic in a Console application first, then create a graphical WPF front-end for that same logic.

### 4. The Importance of "Wiring Things Up"
In WPF, our main job today is "wiring up" the UI. The C# methods we write for the console app (the "business logic") can often be reused directly. The `Button_Click` event handlers will be the glue that connects our XAML buttons and text boxes to our powerful C# logic methods.

---
