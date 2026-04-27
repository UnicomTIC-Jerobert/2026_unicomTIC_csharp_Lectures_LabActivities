## 💻 Lab Activities (6 Hours) - Vending Machine Project

### **Objective**
To design and build a complete application from scratch by breaking down the problem and integrating variables, conditional logic, loops, and methods into a coherent structure for both Console and WPF.

### **Part 1: The Console Logic Core (Activities 1-8)**

#### **Activity 1 (~30 mins): Project Setup & Data Structures**
*   **Concept:** Initializing the project and storing data.
*   **Task:** Create a new Console App `Day5_VendingMachine_Console`. In `Program.cs`, inside the `Main` method, set up the vending machine's data. For now, we'll use simple variables.
    ```csharp
    // Item 1
    string itemName1 = "Crisps";
    double itemPrice1 = 1.50;
    int itemStock1 = 5;

    // Item 2
    string itemName2 = "Chocolate Bar";
    double itemPrice2 = 1.25;
    int itemStock2 = 7;

    // Item 3
    string itemName3 = "Soda Can";
    double itemPrice3 = 2.00;
    int itemStock3 = 3;

    double userBalance = 0.0;
    ```

#### **Activity 2 (~30 mins): The Display Menu Method**
*   **Concept:** Creating a `void` method to handle a repetitive display task.
*   **Task:** Create a new method `public static void DisplayMenu(string name, double price, int stock)`. This method should print a single item's details in a formatted way, like `"1. Crisps | Price: $1.50 | Stock: 5"`. Now create a "master" display method that calls this helper method for all your items.

#### **Activity 3 (~30 mins): The Main Application Loop**
*   **Concept:** Using a `do-while` loop to keep the application running.
*   **Task:** In your `Main` method, create a `do-while` loop. Inside the loop, call your master display menu method and add an option for the user to exit (e.g., "4. Exit"). The loop should continue as long as the user's choice is not '4'.

#### **Activity 4 (~30 mins): Getting and Validating User Input**
*   **Concept:** Creating a method that returns a value and handles basic validation.
*   **Task:** Create a method `public static int GetUserChoice()`. This method should prompt the user for their selection, read the input, parse it to an `int`, and `return` it. Add a simple `if` statement to check if the choice is valid (e.g., between 1 and 4). If not, return an invalid marker like `-1`.

#### **Activity 5 (~35 mins): Handling the User's Choice**
*   **Concept:** Using `if-else if` or `switch` to act on the user's input.
*   **Task:** Inside your `do-while` loop in `Main`, call `GetUserChoice()`. Use a `switch` statement based on the returned choice. For `case 1`, `case 2`, and `case 3`, print a message like "You selected Crisps." For `case 4`, print "Goodbye!". For the `default` case (or your invalid marker), print "Invalid selection."

#### **Activity 6 (~35 mins): The Transaction Logic**
*   **Concept:** Combining conditionals to manage a complex process.
*   **Task:** Create a new method `public static double ProcessTransaction(double itemPrice, int itemStock, double currentBalance)`. This method should:
    1.  Check `if (itemStock <= 0)`. If so, print "Item is out of stock." and `return` the `currentBalance` unchanged.
    2.  If in stock, ask the user to insert money and read the input.
    3.  Check `if (insertedMoney < itemPrice)`. If so, print "Insufficient funds." and `return` the `currentBalance` unchanged.
    4.  If everything is successful, calculate the change (`insertedMoney - itemPrice`), print a success message including the change, and `return` the new balance.

#### **Activity 7 (~30 mins): Updating Data**
*   **Concept:** Modifying variables based on program events.
*   **Task:** Now you need to update the stock. This is tricky because methods can't easily modify variables outside their scope. For now, we will handle it in `Main`. In the `switch` statement, *after a successful transaction*, decrement the correct stock variable (e.g., `itemStock1--;`).

#### **Activity 8 (~25 mins): Final Code Polish**
*   **Concept:** Refactoring for readability.
*   **Task:** Read through your `Main` method. It's probably getting long. Clean it up. Ensure that complex logic is handled by methods and that the main loop is easy to read and understand. Add comments where necessary.

---

### **Part 2: The WPF Graphical User Interface (Activities 9-10)**

#### **Activity 9 (~50 mins): WPF UI Design**
*   **Concept:** Translating a text-based interface into a graphical one.
*   **Task:** Create a new WPF App `Day5_VendingMachine_WPF`. Design an interface that includes:
    *   `GroupBox`es or `Border`s for each item. Inside each, have `TextBlock`s to display the item's name, price, and current stock.
    *   A `Button` for each item to select it.
    *   A `TextBox` for the user to "insert" money.
    *   A central `TextBlock` to act as a status display (e.g., "Please make a selection", "Insufficient funds", "Your change is $...").

#### **Activity 10 (~50 mins): Wiring up the UI to the Logic**
*   **Concept:** Connecting UI events to the C# business logic.
*   **Task:**
    1.  Copy the logic methods you wrote for the console app (like `ProcessTransaction`) into your `MainWindow.xaml.cs` file (you'll need to make them `private` instead of `public static`).
    2.  Copy your data variables (item names, prices, stock) into the `MainWindow` class as member variables.
    3.  Create a `Click` event for the "Crisps" button. Inside this event:
        *   Read the amount of money from the "insert money" `TextBox`.
        *   Call your `ProcessTransaction` logic method, passing in the price and stock for crisps.
        *   Update the status `TextBlock` with the result.
        *   If successful, decrement the crisps stock variable and update the stock `TextBlock` on the UI.
    4.  Repeat this for the other item buttons.

---
