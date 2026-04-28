## 🎓 Daily Quiz (End of Day)

**Instructions:** Choose the best answer for each question.

1.  An interface primarily defines a...
    a) "is-a" relationship
    b) "has-a" relationship
    c) "can-do" relationship
    d) "uses-a" relationship

2.  What can an interface contain?
    a) Method implementations and fields.
    b) Constructors and fields.
    c) Method signatures and properties only.
    d) Private methods.

3.  By convention, interface names in C# start with...
    a) A lowercase 'i'
    b) An underscore `_`
    c) The keyword `interface`
    d) A capital 'I'

4.  A single class can inherit from ___ base class(es) and implement ___ interface(s).
    a) one, one
    b) many, one
    c) one, many
    d) many, many

5.  What happens if a class implements an interface but forgets to provide an implementation for one of its methods?
    a) A warning is generated.
    b) An error occurs at run-time.
    c) A compilation error occurs.
    d) Nothing, it is allowed.

6.  Which keyword combination is used for implementing an inherited method vs. an interface method?
    a) `virtual`/`override` for both.
    b) No keyword for inheritance, `implements` for interface.
    c) `virtual`/`override` for inheritance, no special keyword for interface.
    d) `implements` for inheritance, `virtual`/`override` for interface.

7.  Which of the following is a key advantage of interfaces over abstract classes?
    a) Interfaces can have constructors.
    b) Interfaces allow a class to "inherit" from multiple sources.
    c) Interfaces can have implemented methods.
    d) Interfaces can have private fields.

8.  Given `interface ITest { void Go(); }`, which class definition is valid?
    a) `public class MyClass : ITest { }`
    b) `public class MyClass : ITest { public void Go() { /* ... */ } }`
    c) `public class MyClass implements ITest { public void Go() { /* ... */ } }`
    d) `public class MyClass { public override void Go() { /* ... */ } }`

9.  If `Car` and `Boat` both implement `IMovable`, which collection type can hold both?
    a) `List<Vehicle>`
    b) `List<object>`
    c) `List<IMovable>`
    d) Both b and c are correct.

10. What is the primary purpose of using interfaces in software design?
    a) To increase performance.
    b) To reduce the number of classes.
    c) To achieve loose coupling and improve testability.
    d) To force all objects to be the same type.

11. Can an interface have a constructor?
    a) Yes
    b) No
    c) Only if it is public.
    d) Only if it inherits from another interface.

12. Can an interface inherit from another interface?
    a) Yes, this is a common way to extend contracts.
    b) No, interfaces cannot participate in inheritance.
    c) Only if the base interface is empty.
    d) Only a single level of inheritance is allowed.

13. You would choose an **abstract class** over an interface when...
    a) You want to define a capability for unrelated classes.
    b) You want to provide common, implemented functionality for a group of related derived classes.
    c) You want to support multiple inheritance.
    d) You want to create a `static` class.

14. `public class Report : ILoggable, ISavable` is an example of...
    a) Method overriding
    b) Multiple inheritance
    c) Multiple interface implementation
    d) Method overloading

15. In WPF, interfaces are crucial for design patterns like MVVM because they...
    a) Allow the View and ViewModel to be connected without knowing about each other's concrete types.
    b) Automatically update the UI when a property changes.
    c) Define the colors and styles of UI elements.
    d) Handle database connections.

16. To get the `SelectedItem` from a `ListBox` and use its interface method, what must you do first?
    a) Nothing, you can call it directly.
    b) Cast the `SelectedItem` (which is of type `object`) to the interface type.
    c) Override the `ToString()` method.
    d) Use a `for` loop.

17. If a class `MyClass` implements `IDisposable`, it means `MyClass`...
    a) is a disposable (temporary) object.
    b) has a method named `Dispose()` that can be called.
    c) is a base class.
    d) cannot be instantiated.

18. What is wrong with this interface definition? `public interface IWorker { public int Id; void Work(); }`
    a) Methods in an interface cannot have a `void` return type.
    b) The method `Work()` has no implementation.
    c) Interfaces cannot contain fields like `Id`.
    d) The name `IWorker` is invalid.

19. Which of the following CANNOT implement an interface?
    a) A `struct`
    b) An `enum`
    c) A `class`
    d) An `abstract class`

20. Using a `List<IPlayable>` to manage `Song` and `Video` objects is an example of...
    a) Encapsulation
    b) Inheritance
    c) Abstraction and Polymorphism
    d) Data Hiding

---
<details>
  <summary><strong>ANSWER KEY</strong></summary>
  
  1. **c)** "can-do" relationship
  2. **c)** Method signatures and properties only.
  3. **d)** A capital 'I'
  4. **c)** one, many
  5. **c)** A compilation error occurs.
  6. **c)** `virtual`/`override` for inheritance, no special keyword for interface.
  7. **b)** Interfaces allow a class to "inherit" from multiple sources.
  8. **b)** `public class MyClass : ITest { public void Go() { /* ... */ } }`
  9. **d)** Both b and c are correct. (All objects can be stored in `List<object>`, but `List<IMovable>` is the more specific and better choice).
  10. **c)** To achieve loose coupling and improve testability.
  11. **b)** No
  12. **a)** Yes, this is a common way to extend contracts.
  13. **b)** You want to provide common, implemented functionality for a group of related derived classes.
  14. **c)** Multiple interface implementation
  15. **a)** Allow the View and ViewModel to be connected without knowing about each other's concrete types.
  16. **b)** Cast the `SelectedItem` (which is of type `object`) to the interface type.
  17. **b)** has a method named `Dispose()` that can be called.
  18. **c)** Interfaces cannot contain fields like `Id`.
  19. **b)** An `enum`
  20. **c)** Abstraction and Polymorphism
</details>
