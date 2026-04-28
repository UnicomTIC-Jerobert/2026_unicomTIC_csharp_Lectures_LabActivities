
## 🎓 Daily Quiz (End of Day)

**Instructions:** Choose the best answer for each question.

1.  Polymorphism allows an object of a derived class to be treated as an object of its...
    a) Sibling class
    b) Child class
    c) Base class
    d) `object` class only

2.  Which keyword is used in a **base class** to indicate that a method can be overridden?
    a) `override`
    b) `virtual`
    c) `new`
    d) `base`

3.  Which keyword is used in a **derived class** to provide a new implementation for a base class method?
    a) `override`
    b) `virtual`
    c) `new`
    d) `base`

4.  What is the main benefit of polymorphism?
    a) It makes code run faster.
    b) It reduces the memory footprint of objects.
    c) It allows for writing flexible, reusable code that can work with objects of different but related types.
    d) It enforces that all objects must be of the same type.

5.  Given `List<Animal> animals = new List<Animal>();`, which of the following lines is valid if `Dog` inherits from `Animal`?
    a) `animals.Add(new Dog());`
    b) `animals = new List<Dog>();`
    c) `Dog d = new Animal();`
    d) All of the above are valid.

6.  What is the output of the following code?
    ```csharp
    Animal myPet = new Dog(); // Dog inherits from Animal
    myPet.MakeSound(); // Dog overrides MakeSound to print "Woof!"
    ```
    a) The Animal's generic sound.
    b) "Woof!"
    c) The code will not compile.
    d) An error will occur at runtime.

7.  Every class in C# implicitly inherits from which base class?
    a) `System.Base`
    b) `Program`
    c) `Object`
    d) `Main`

8.  What is the most commonly overridden method from the `object` class?
    a) `Equals()`
    b) `GetHashCode()`
    c) `GetType()`
    d) `ToString()`

9.  If a base class method is NOT marked as `virtual`, can a derived class `override` it?
    a) Yes, without any issues.
    b) Yes, but it will cause a warning.
    c) No, it will cause a compilation error.
    d) Only if the derived class is `sealed`.

10. What is the difference between Method Overriding and Method Overloading?
    a) They are the same thing.
    b) Overriding provides a new implementation for an inherited method; Overloading provides multiple methods with the same name but different parameters.
    c) Overloading is for base classes; Overriding is for derived classes.
    d) Overriding changes the method signature; Overloading does not.

11. If `Square` inherits from `Shape`, what is this process called? `Shape s = new Square();`
    a) Downcasting
    b) Upcasting
    c) Sidecasting
    d) Recasting

12. The `virtual` keyword can be applied to...
    a) Methods, properties, and constructors.
    b) Methods and properties only.
    c) Methods only.
    d) Any member of a class.

13. What is the output?
    ```csharp
    public class A { public virtual void P() { Console.Write("A"); } }
    public class B : A { public override void P() { Console.Write("B"); } }
    A myA = new B();
    myA.P();
    ```
    a) A
    b) B
    c) AB
    d) An error.

14. The decision of which overridden method to call is made at...
    a) Compile-time
    b) Run-time
    c) Link-time
    d) Design-time

15. What does the `base` keyword let you do from within an overridden method?
    a) Call the base class's version of the method.
    b) Prevent the method from being called.
    c) Call the derived class's version of the method.
    d) Access private members of the base class.

16. Which statement is true about `abstract` methods?
    a) They are the same as `virtual` methods.
    b) An abstract method has no implementation and MUST be overridden by derived classes.
    c) They cannot be overridden.
    d) They must be private.

17. If you have a `List<Shape>` containing `Circle` and `Square` objects, how can you safely access a `Circle`-only property?
    a) `((Circle)shape).Radius` (This is an unsafe cast).
    b) By using the `is` keyword to check the type first: `if (shape is Circle) { ... }`.
    c) It's not possible.
    d) By overriding the property in the `Shape` class.

18. A class that cannot be instantiated and is meant only to be a base class is likely a(n)...
    a) `sealed` class
    b) `static` class
    c) `private` class
    d) `abstract` class

19. In WPF, why is polymorphism useful for a `ListBox`?
    a) It allows the `ListBox` to display items of different but related types, each with its own `ToString()` representation.
    b) It changes the color of the `ListBox`.
    c) It makes the `ListBox` scroll faster.
    d) It's not useful for a `ListBox`.

20. What is the output of this code?
    ```csharp
    public class X { public virtual void M() { Console.Write("X"); } }
    public class Y : X { }
    Y myY = new Y();
    myY.M();
    ```
    a) Y
    b) X
    c) Nothing.
    d) An error.

---
<details>
  <summary><strong>ANSWER KEY</strong></summary>
  
  1. **c)** Base class
  2. **b)** `virtual`
  3. **a)** `override`
  4. **c)** It allows for writing flexible, reusable code that can work with objects of different but related types.
  5. **a)** `animals.Add(new Dog());`
  6. **b)** "Woof!"
  7. **c)** `Object`
  8. **d)** `ToString()`
  9. **c)** No, it will cause a compilation error.
  10. **b)** Overriding provides a new implementation for an inherited method; Overloading provides multiple methods with the same name but different parameters.
  11. **b)** Upcasting
  12. **b)** Methods and properties only.
  13. **b)** B
  14. **b)** Run-time
  15. **a)** Call the base class's version of the method.
  16. **b)** An abstract method has no implementation and MUST be overridden by derived classes.
  17. **b)** By using the `is` keyword to check the type first: `if (shape is Circle) { ... }`.
  18. **d)** `abstract` class
  19. **a)** It allows the `ListBox` to display items of different but related types, each with its own `ToString()` representation.
  20. **b)** X (Because class Y does not provide an override, it inherits and uses the implementation from X).
</details>
