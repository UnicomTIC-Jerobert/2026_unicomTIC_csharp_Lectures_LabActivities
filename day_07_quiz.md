## 🎓 Daily Quiz (End of Day)

**Instructions:** Choose the best answer for each question.

1.  Inheritance models which type of relationship?
    a) "has-a"
    b) "is-a"
    c) "uses-a"
    d) "knows-a"

2.  In `public class Dog : Animal`, `Animal` is the...
    a) Derived class
    b) Child class
    c) Subclass
    d) Base class

3.  Which member of a base class is **NOT** accessible to a derived class?
    a) `public`
    b) `private`
    c) `protected`
    d) `internal`

4.  The `protected` access modifier allows access...
    a) From anywhere in the program.
    b) Only within the class itself.
    c) Within the class itself AND in any derived classes.
    d) Only from the `Main` method.

5.  What C# syntax is used to indicate inheritance?
    a) `->`
    b) `::`
    c) `:`
    d) `inherits`

6.  Are constructors inherited from the base class?
    a) Yes, always.
    b) No, never.
    c) Only if they are public.
    d) Only if they have parameters.

7.  How does a derived class constructor call its base class constructor?
    a) `super();`
    b) `parent();`
    c) `base()`
    d) `new BaseClass()`

8.  When creating an object of a derived class, which constructor runs first?
    a) The derived class constructor.
    b) The base class constructor.
    c) They run at the same time.
    d) Neither runs unless called explicitly.

9.  If `Car` inherits from `Vehicle`, which statement is true?
    a) Every `Vehicle` is a `Car`.
    b) Every `Car` is a `Vehicle`.
    c) A `Car` "has a" `Vehicle`.
    d) `Car` and `Vehicle` are unrelated.

10. A derived class can...
    a) Add new methods and properties.
    b) Not add any new members.
    c) Only add new methods.
    d) Only add new properties.

11. A class that inherits from another class is called a...
    a) Parent class
    b) Superclass
    c) Subclass
    d) Master class

12. What is wrong with this code?
    `public class Shape { private int id; }`
    `public class Circle : Shape { public void PrintId() { Console.WriteLine(id); } }`
    a) `Circle` cannot inherit from `Shape`.
    b) `id` is private to `Shape` and cannot be accessed in `Circle`.
    c) The `PrintId` method needs to be static.
    d) Nothing is wrong.

13. To fix the code in the previous question, `id` should be declared as...
    a) `public`
    b) `static`
    c) `protected`
    d) `void`

14. The main benefit of inheritance is...
    a) Code reuse and creating a logical hierarchy.
    b) Improved performance.
    c) Reduced memory usage.
    d) Making code harder to understand.

15. A class can inherit from...
    a) Multiple base classes.
    b) Only one base class.
    c) As many base classes as needed, separated by commas.
    d) Zero base classes only.

16. What is the `object` class in .NET?
    a) A class you must create in every project.
    b) The ultimate base class for all types in .NET.
    c) A special class for creating UI elements.
    d) A class that cannot be inherited from.

17. Given `public class A { public A(int x) {} }` and `public class B : A {}`, what is required for class `B` to compile?
    a) Nothing, it will compile fine.
    b) A constructor in `B` that calls `base(some_int_value)`.
    c) Class `A` must have a parameterless constructor.
    d) Class `B` must be abstract.

18. You can prevent a class from being inherited by using which keyword?
    a) `private`
    b) `static`
    c) `const`
    d) `sealed`

19. In WPF, inheritance is often used to...
    a) Create specialized versions of existing UI controls.
    b) Change the color of a button.
    c) Store user login information.
    d) Connect to a database.

20. What is a class hierarchy?
    a) A single class with many methods.
    b) A "tree" of classes where classes inherit from other classes.
    c) A method for sorting objects.
    d) A special type of constructor.

---
<details>
  <summary><strong>ANSWER KEY</strong></summary>
  
  1. **b)** "is-a"
  2. **d)** Base class
  3. **b)** `private`
  4. **c)** Within the class itself AND in any derived classes.
  5. **c)** `:`
  6. **b)** No, never.
  7. **c)** `base()`
  8. **b)** The base class constructor.
  9. **b)** Every `Car` is a `Vehicle`.
  10. **a)** Add new methods and properties.
  11. **c)** Subclass
  12. **b)** `id` is private to `Shape` and cannot be accessed in `Circle`.
  13. **c)** `protected`
  14. **a)** Code reuse and creating a logical hierarchy.
  15. **b)** Only one base class.
  16. **b)** The ultimate base class for all types in .NET.
  17. **b)** A constructor in `B` that calls `base(some_int_value)`.
  18. **d)** `sealed`
  19. **a)** Create specialized versions of existing UI controls.
  20. **b)** A "tree" of classes where classes inherit from other classes.
</details>
