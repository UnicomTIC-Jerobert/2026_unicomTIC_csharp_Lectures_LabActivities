## 💻 Lab Activities (6 Hours)

### **Objective**
To master the use of `Dictionary<TKey, TValue>` for fast key-based lookups, to understand the concept of key-value pairs, and to apply this collection in both data processing and UI scenarios.

### **Activity 1 (~30 mins): Basic Dictionary Creation**
*   **Concept:** Basic syntax for creating and adding to a dictionary.
*   **Console:** Create `Day13_Activity1_Dictionary`.
    1.  Add `using System.Collections.Generic;`.
    2.  Create a `Dictionary<string, string>` to store country-capital pairs. Call it `capitals`.
    3.  Use the `.Add()` method to add three entries: "UK" -> "London", "France" -> "Paris", "Japan" -> "Tokyo".
    4.  Print the `.Count` of the dictionary.

### **Activity 2 (~35 mins): Accessing and Modifying Data**
*   **Concept:** Using the indexer `[]` and checking for keys.
*   **Console:** In the same project:
    1.  Access and print the capital of France using the key "France": `capitals["France"]`.
    2.  Use `ContainsKey()` to check if the dictionary contains the key "Germany". Print a message based on the result.
    3.  Try to add a duplicate key: `capitals.Add("UK", "Manchester");`. Wrap this in a `try-catch` block to see the exception, or use `ContainsKey` to prevent the error.
    4.  Change the value for an existing key: `capitals["Japan"] = "New Tokyo";`.

### **Activity 3 (~35 mins): Iterating Over a Dictionary**
*   **Concept:** Using `foreach` with `KeyValuePair`.
*   **Console:** Create `Day13_Activity3_Iteration`.
    1.  Create a dictionary to store student IDs and their scores: `Dictionary<int, int> studentScores`. Populate it with at least 5 students.
    2.  Use a `foreach` loop with `KeyValuePair<int, int>` to iterate through the dictionary.
    3.  Inside the loop, print a formatted string for each entry, like `"Student ID: 101, Score: 88"`.

### **Activity 4 (~40 mins): Word Frequency Counter**
*   **Concept:** A classic dictionary problem: counting occurrences.
*   **Console:** Create `Day13_Activity4_WordCount`.
    1.  Start with a sample sentence `string text = "the quick brown fox jumps over the lazy dog";`.
    2.  Split the sentence into an array of words using `text.Split(' ');`.
    3.  Create an empty `Dictionary<string, int>`.
    4.  Loop through your array of words. For each word:
        *   If the dictionary already `ContainsKey()` the word, increment its value: `wordCounts[word]++;`.
        *   If it doesn't contain the key, `.Add()` the word with a value of 1.
    5.  After the loop, iterate through your dictionary and print each word and its count.

### **Activity 5 (~40 mins): Dictionary of Objects**
*   **Concept:** Using custom objects as the `TValue`.
*   **Console:** Create `Day13_Activity5_Objects`.
    1.  Create a `Product` class (`Name`, `Price`, `Stock`).
    2.  In `Main`, create a `Dictionary<int, Product>` where the key is a unique Product ID (`int`).
    3.  Add three new `Product` objects to the dictionary, using product IDs like 1001, 1002, 1003 as keys.
    4.  Prompt the user: "Enter a Product ID to look up:".
    5.  Read the user's input, parse it to an `int`.
    6.  Use `TryGetValue()` to safely look up the product. If it's found, print its details. If not, print "Product not found."

### **Activity 6 (~40 mins): WPF Phone Book**
*   **Concept:** Using a dictionary as the backend for a fast UI lookup.
*   **WPF:** Create `Day13_Activity6_WPF_PhoneBook`.
    1.  Design a UI with:
        *   `TextBox`es for Name and Phone Number, and an "Add/Update Contact" `Button`.
        *   A `ListBox` to display the names of all contacts.
        *   A "Look Up" `Button` and a `TextBlock` to display the looked-up number.
    2.  In the code-behind, create a `private Dictionary<string, string> phoneBook = new Dictionary<string, string>();`. The key will be the name.

### **Activity 7 (~40 mins): Implementing the WPF Phone Book**
*   **Concept:** Wiring up the dictionary logic to the UI.
*   **WPF:** In the same project:
    1.  Implement the "Add/Update Contact" button. When clicked, it should add the new entry or update the existing one. You can do this easily with the indexer: `phoneBook[name] = phoneNumber;`. After adding/updating, refresh the `ListBox` with all the keys from the dictionary.
    2.  Implement the `ListBox`'s `SelectionChanged` event. When a user clicks a name, it should populate the Name `TextBox`.
    3.  Implement the "Look Up" button. It should take the name from the `TextBox`, look it up in the `phoneBook` dictionary, and display the corresponding phone number in the `TextBlock`.

### **Activity 8 (~15 mins): Git Submission**
*   **Task:** Stage, commit, and push your new projects to GitHub with the message: `"Day 13 Labs: Dictionary and Key-Value Pairs"`.

---
