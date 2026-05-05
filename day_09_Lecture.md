# Week 2, Day 4: Interfaces

## 📖 Lecture Notes (1 Hour)

### 1. Introduction: The Limits of Inheritance
Inheritance is powerful, but it has a fundamental limitation: it models an **"is-a"** relationship. A `Dog` is an `Animal`. This makes sense. But what if we want to describe a *capability* that is shared by completely unrelated things?

Consider the ability to be saved to a file. A `Document` can be saved. A `GameCharacter` can be saved. A `UserSettings` object can be saved. But a `Document` is not a `GameCharacter`. They don't share a common "is-a" parent. How can we write a single method, `SaveObjectToFile(objectToSave)`, that can handle all of them?

### 2. Interfaces: A "Can-Do" Contract
An **interface** solves this problem. An interface is not a blueprint for an object; it is a **contract** for behavior. It defines a set of public methods, properties, events, or indexers that a class *promises* to implement.

*   Inheritance is an **"is-a"** relationship (a `Car` is a `Vehicle`).
*   An Interface is a **"can-do"** relationship (a `Car` can be `IDrivable`; a `Person` can be `IDrivable`).

An interface contains no implementation—only the signatures of the members.

### 3. Interface Syntax
By convention, interface names start with a capital `I`.

```csharp
// 1. The Interface Definition (The Contract)
// This contract says that anything that wants to be "savable" MUST
// provide a method called Save() and a property called HasUnsavedChanges.
public interface ISavable
{
    bool HasUnsavedChanges { get; set; }
    void Save();
}

// 2. Class Implementation (Fulfilling the Contract)
public class Document : ISavable // Note: Same ':' syntax as inheritance
{
    // The class MUST provide a concrete implementation for all interface members.
    public bool HasUnsavedChanges { get; set; }
    
    public void Save()
    {
        Console.WriteLine("Saving the document to a file...");
        HasUnsavedChanges = false;
    }
}

// 3. Another, unrelated class can also fulfill the contract.
public class GameCharacter : ISavable
{
    public bool HasUnsavedChanges { get; set; }

    public void Save()
    {
        Console.WriteLine("Saving character stats to the server...");
        HasUnsavedChanges = false;
    }
}
```

### 4. Polymorphism with Interfaces
This is where the true power lies. Just like with base classes, you can treat objects by their interface type. This allows you to write code that is completely decoupled from the concrete classes.

```csharp
// Create a list that can hold ANYTHING that is "ISavable".
List<ISavable> thingsToSave = new List<ISavable>();

Document myDoc = new Document();
GameCharacter myChar = new GameCharacter();

thingsToSave.Add(myDoc);
thingsToSave.Add(myChar);

// Now we can loop through and save everything, without needing to know
// if it's a Document, a Character, or something else entirely.
foreach (ISavable item in thingsToSave)
{
    item.Save();
}
// Output:
// Saving the document to a file...
// Saving character stats to the server...
```

### 5. Key Differences: Interface vs. Abstract Class
| Feature | Interface | Abstract Class |
| :--- | :--- | :--- |
| **Multiple Implementation** | A class can implement **many** interfaces. | A class can inherit from only **one** abstract class. |
| **Implementation** | Contains **no** implementation (only method signatures). | **Can** contain implementation for some methods. |
| **Constructors / Fields** | **Cannot** have constructors or fields. | **Can** have constructors and fields. |
| **Purpose** | To define a "can-do" capability. | To provide a common base for a "is-a" hierarchy. |

**Rule of Thumb:** Prefer interfaces to define contracts. Use abstract classes when you need to share common, implemented code among several derived classes.

### 6. Multiple Interfaces
A class can implement as many interfaces as it needs. This is a huge advantage over single inheritance.

```csharp
public interface ILoggable { void Log(string message); }

// This class promises to fulfill TWO contracts.
public class Report : ISavable, ILoggable
{
    public bool HasUnsavedChanges { get; set; }
    public void Save() { /* ... */ }
    public void Log(string message) { /* ... */ }
}
```

---
