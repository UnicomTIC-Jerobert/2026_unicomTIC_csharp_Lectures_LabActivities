# Week 2, Day 5: OOP Mini-Project - Zoo Management

## 📖 Lecture Notes (1 Hour)

### 1. Weekly Review: The Four Pillars of OOP
This week, we moved beyond simple scripts and learned the principles that power all modern software development. Let's review the four pillars we've covered:
*   **Pillar 1: Encapsulation (Classes & Objects)**
    *   We learned to bundle related data (properties) and behaviors (methods) into a single unit called a class. This hides complexity and creates reusable blueprints.
*   **Pillar 2: Inheritance ("is-a" Relationship)**
    *   We learned to create new classes that inherit members from a base class. This promotes code reuse and establishes a logical hierarchy (e.g., a `Manager` is an `Employee`). We used the `protected` keyword to share data with derived classes only.
*   **Pillar 3: Polymorphism ("many forms")**
    *   We learned to treat derived class objects as instances of their base class. Using `virtual` and `override`, we allowed each object to provide its own specific behavior for a common method (`MakeSound()`), making our code incredibly flexible.
*   **Pillar 4: Abstraction (Interfaces & Abstract Classes)**
    *   We learned to define **contracts** with interfaces (a "can-do" relationship) and provide partial implementations with abstract classes. This decouples our code, allowing us to write systems that depend on capabilities, not on concrete types.

### 2. Today's Project: A Simple Zoo Simulator
We will combine all four pillars to build a zoo management system. This project will require us to think about the relationships between different types of animals.
*   **The Problem:** A zoo contains many different animals. We need a way to manage all of them in a single collection. We want to be able to command all animals to make their sound, or tell all flying animals to fly, without needing to know the specific type of each animal.

### 3. Our Design Plan (Problem Decomposition)
1.  **Base Abstraction (`Animal`):** We'll start with a general `abstract` class called `Animal`. It will contain common properties like `Name` and `Age`, and define `abstract` methods like `MakeSound()` and `Move()`, because every animal does these things, but they all do them differently.
2.  **Inheritance (`Mammal`, `Bird`):** We'll create more specific abstract classes like `Mammal` and `Bird` that inherit from `Animal`. They might add properties specific to their group (e.g., `FurColor` for `Mammal`).
3.  **Concrete Classes (`Lion`, `Eagle`):** We'll create concrete classes that inherit from `Mammal` or `Bird`. These will provide the *actual* implementations for the abstract methods.
4.  **Interfaces (`IFlyable`):** What about flying? Most birds fly, but not all (like penguins). Some mammals fly (bats). A simple inheritance model doesn't work. We'll create an `IFlyable` interface to describe the *capability* of flight, and only specific animals will implement it.
5.  **Polymorphism (The `Zoo`):** The main application will have a single `List<Animal>`. We will loop through this list and call methods on each animal, trusting polymorphism to execute the correct, specific behavior for each one.

This design forces us to use every concept from this week and demonstrates how they work together to create a powerful, flexible, and well-organized system.

---
