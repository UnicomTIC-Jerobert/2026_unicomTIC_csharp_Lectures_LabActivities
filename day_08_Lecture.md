# Week 2, Day 3: Polymorphism

## 📖 Lecture Notes (1 Hour)

### 1. Introduction: The Problem of Specificity
Yesterday, we created an `Animal` hierarchy with `Dog`s and `Cat`s. Imagine you want to manage all the animals in a pet store. You would need a `List<Dog>` for the dogs, a `List<Cat>` for the cats, a `List<Fish>` for the fish, and so on. This is inflexible. If you want to feed all the animals, you'd have to loop through each separate list.

What if we could put all our animals into a single `List<Animal>` and treat them all as just "animals," letting each one behave in its own special way automatically? This is exactly what **Polymorphism** allows us to do.

### 2. Polymorphism: The "Many Forms" Principle
The word Polymorphism comes from Greek and means "many forms." In OOP, it's the ability for an object of a derived class to be treated as an object of its base class.

*   A `Manager` object can take the form of an `Employee`.
*   A `Circle` object can take the form of a `Shape`.
*   A `Dog` object can take the form of an `Animal`.

This allows us to write more general, flexible, and decoupled code. We can write a method that works with `Animal`s, and it will automatically work correctly with `Dog`s, `Cat`s, or any other `Animal` type we create in the future, without changing a single line of code.

### 3. The "How": Method Overriding
Polymorphism is primarily achieved through **Method Overriding**. This allows a derived class to provide its own specific implementation of a method that is already defined in its base class.

There are two essential keywords:
*   **`virtual` (in the Base Class):** This keyword says, "This method's implementation *can be replaced* by a derived class." It's an opt-in system.
*   **`override` (in the Derived Class):** This keyword says, "I am *providing a new implementation* for the virtual method from my base class."

```csharp
public class Animal
{
    // By marking this as 'virtual', we allow derived classes to override it.
    public virtual void MakeSound()
    {
        Console.WriteLine("The animal makes a generic sound.");
    }
}

public class Dog : Animal
{
    // We 'override' the base method to provide a Dog-specific implementation.
    public override void MakeSound()
    {
        Console.WriteLine("Woof!");
    }
}

public class Cat : Animal
{
    // The Cat class also provides its own specific implementation.
    public override void MakeSound()
    {
        Console.WriteLine("Meow!");
    }
}
```

### 4. Polymorphism in Action
Now, let's see the magic. We can create a list of `Animal`s, but fill it with `Dog`s and `Cat`s.

```csharp
// The variable 'myDog' is of type Animal, but the object it holds is a Dog.
Animal myDog = new Dog(); 
Animal myCat = new Cat();

List<Animal> pets = new List<Animal>();
pets.Add(myDog);
pets.Add(myCat);

foreach (Animal pet in pets)
{
    // The magic happens here!
    // C# knows the ACTUAL type of the object in the list.
    // If 'pet' holds a Dog, it calls the Dog's version.
    // If 'pet' holds a Cat, it calls the Cat's version.
    pet.MakeSound(); 
}

// Output:
// Woof!
// Meow!
```

### 5. Overriding `ToString()`
Every object in C# automatically inherits from the base `object` class. This class has a `public virtual string ToString()` method. This is the most common method you will ever override. By providing your own implementation, you can control how your object is represented as text.

```csharp
public class Book
{
    public string Title { get; set; }
    public string Author { get; set; }

    // Override the default ToString() method from the 'object' class
    public override string ToString()
    {
        return $"{Title} by {Author}";
    }
}

Book myBook = new Book { Title = "1984", Author = "George Orwell" };
Console.WriteLine(myBook); // Automatically calls our overridden ToString()
// Output: 1984 by George Orwell
```

---
