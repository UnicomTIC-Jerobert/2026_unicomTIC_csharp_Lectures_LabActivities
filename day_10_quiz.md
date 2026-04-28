## 🎓 Weekly Review Quiz (End of Day)

**Instructions:** This quiz covers all topics from Week 2. Choose the best answer.

1.  Which pillar of OOP involves bundling data and methods into a single unit?
    a) Inheritance b) Polymorphism c) Encapsulation d) Abstraction
2.  In `public class Manager : Employee`, `Employee` is the...
    a) Derived Class b) Interface c) Base Class d) Object
3.  The `protected` keyword makes a member accessible in...
    a) Only the base class. b) The base class and all derived classes. c) Anywhere in the program. d) Only derived classes, not the base class.
4.  What does the `virtual` keyword signify on a method?
    a) The method must be implemented by derived classes. b) The method can be overridden by derived classes. c) The method cannot be changed. d) The method is part of an interface.
5.  What does the `override` keyword signify on a method?
    a) It creates a new method with the same name. b) It hides the base class method. c) It provides a new implementation for a `virtual` base class method. d) It marks the method as obsolete.
6.  An `interface` is best described as a...
    a) Blueprint for an object. b) Contract for capabilities. c) Base class with some implementation. d) A static helper class.
7.  A class can inherit from how many base classes and implement how many interfaces?
    a) 1, 1 b) 1, Many c) Many, 1 d) Many, Many
8.  If `Dog` and `Cat` inherit from `Animal`, and `MakeSound` is overridden, what happens in a `List<Animal>`?
    a) All objects will call the `Animal` version of `MakeSound`. b) An error will occur. c) Each object will call its own specific version of `MakeSound`. d) You cannot create a `List<Animal>` with `Dog`s and `Cat`s.
9.  A constructor in a derived class must call its base class constructor using what keyword?
    a) `super()` b) `parent()` c) `new()` d) `base()`
10. Which is a key difference between an abstract class and an interface?
    a) An abstract class can have implemented methods, while an interface cannot. b) An interface can have constructors. c) A class can inherit from multiple abstract classes. d) An interface can have private fields.
11. The process of treating a `Dog` object as an `Animal` is called...
    a) Downcasting b) Upcasting c) Encapsulation d) Instantiation
12. Overriding the `ToString()` method allows you to...
    a) Convert any object to an integer. b) Provide a custom string representation for your object. c) Make your object saveable. d) Change the object's name.
13. If a base class method is NOT `virtual` or `abstract`, can it be overridden?
    a) Yes b) No c) Only if it is public d) Only if it is protected
14. An `abstract` method is a method that...
    a) Is virtual by default. b) Has no implementation and must be overridden. c) Is optional to implement. d) Can only be called from the base class.
15. If `Car` and `Person` both implement `ISavable`, you can add both to a...
    a) `List<Car>` b) `List<Person>` c) `List<ISavable>` d) `List<object>`
16. The `is` keyword is used to...
    a) Check if two objects are the same instance. b) Check if an object is of a certain type or implements an interface. c) Assign a new type to an object. d) Create a new object.
17. What is the output? `A myObj = new B(); myObj.DoWork();` (where B inherits from A and overrides `DoWork`).
    a) The `DoWork` method from class A. b) The `DoWork` method from class B. c) A compile-time error. d) A run-time error.
18. You would choose an interface over an abstract class when...
    a) You need to provide common implemented code. b) You are defining a capability that will be shared by unrelated classes. c) You are defining the core identity of an object hierarchy. d) You need to have private fields.
19. What does the `sealed` keyword on a class prevent?
    a) Instantiation b) Method overriding c) Inheritance from that class d) Method overloading
20. The four pillars of OOP work together primarily to...
    a) Make code run faster. b) Create well-organized, flexible, reusable, and maintainable software. c) Reduce the final size of the application file. d) Eliminate the need for comments.

---
<details>
  <summary><strong>ANSWER KEY</strong></summary>
  
  1. **c)** Encapsulation
  2. **c)** Base Class
  3. **b)** The base class and all derived classes.
  4. **b)** The method can be overridden by derived classes.
  5. **c)** It provides a new implementation for a `virtual` base class method.
  6. **b)** Contract for capabilities.
  7. **b)** 1, Many
  8. **c)** Each object will call its own specific version of `MakeSound`.
  9. **d)** `base()`
  10. **a)** An abstract class can have implemented methods, while an interface cannot.
  11. **b)** Upcasting
  12. **b)** Provide a custom string representation for your object.
  13. **b)** No
  14. **b)** Has no implementation and must be overridden.
  15. **c)** `List<ISavable>` (This is the most specific and best answer).
  16. **b)** Check if an object is of a certain type or implements an interface.
  17. **b)** The `DoWork` method from class B.
  18. **b)** You are defining a capability that will be shared by unrelated classes.
  19. **c)** Inheritance from that class
  20. **b)** Create well-organized, flexible, reusable, and maintainable software.
</details>
