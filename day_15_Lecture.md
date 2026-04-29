Of course. Let's proceed to **Week 3, Day 5**. This will be the capstone mini-project for the week, designed to integrate everything the students have learned about Arrays, Lists, Dictionaries, and especially LINQ, into a single, functional application.

This curriculum follows your established structure: 1-hour lecture, a step-by-step guided mini-project, and a comprehensive 20-question weekly review quiz.

***

# Week 3, Day 5: Collections Mini-Project

## 📖 Lecture Notes (1 Hour)

### 1. Weekly Review: The Tools for Managing Data
This week has been entirely focused on managing groups of data. Let's review the powerful tools we've added to our C# toolbox:
*   **Arrays (`T[]`):** Our foundational collection. Fast, simple, but **fixed-size**. Perfect for when you know the number of elements will not change.
*   **Lists (`List<T>`):** The workhorse of C# collections. A "smart" array that is **dynamic**, growing and shrinking as needed. It's our default choice for storing an ordered sequence of items.
*   **Dictionaries (`Dictionary<TKey, TValue>`):** Our high-performance lookup collection. It stores **key-value pairs** for near-instantaneous retrieval based on a unique key. It is unordered.
*   **LINQ (Language-Integrated Query):** The modern, declarative way to query and manipulate all of these collections. With methods like `Where`, `Select`, `OrderBy`, and `Sum`, we can write complex data operations in a clean, readable way.

### 2. Today's Project: Student Roster Management System
We will combine all these concepts to build a student management system. This is a very common type of application that almost every business needs in some form (for customers, products, employees, etc.).

### 3. Design Plan & Choosing the Right Collection
A good developer doesn't just use a collection; they choose the *right* collection for the job. Let's break down our project and decide.

*   **The Core Data Store:** We will have a central list of all students. We'll be adding and removing students, so a **`List<Student>`** is the perfect choice. An array would be too rigid.
*   **Fast Lookups by ID:** We will frequently need to find a student by their unique `StudentID`. Searching a list of thousands of students is slow. Therefore, we will also maintain a **`Dictionary<int, Student>`** where the key is the `StudentID`. This gives us the best of both worlds: a main list for general processing and a dictionary for instant lookups.
*   **Grouping and Analysis (LINQ):** We'll need to answer questions like:
    *   "Who are the top 5 performing students?"
    *   "What is the average grade for all students?"
    *   "Show me all students in the 'Computer Science' major."
    *   "Find all students whose last name is 'Smith'."
    This is where **LINQ** will be our primary tool. We will write queries against our main `List<Student>` to get these answers quickly and efficiently.

### 4. Application Architecture
1.  **Model (`Student` class):** A simple class to hold the data for a single student (`ID`, `FirstName`, `LastName`, `Major`, `GPA`).
2.  **Repository (`StudentRepository` class):** This is a new concept. A "Repository" is a class whose only job is to manage a collection of data. It will contain our `List` and `Dictionary`. All the code for adding, removing, and querying students will go inside this class. This encapsulates our data management logic.
3.  **UI (Console and WPF):** The user interface will interact *only* with the `StudentRepository`. It will ask the repository to perform actions ("add this student", "find all honors students") and will display the data that the repository returns. This separation of concerns is a critical software design principle.

---
