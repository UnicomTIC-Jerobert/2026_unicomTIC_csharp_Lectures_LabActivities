## 🎓 Daily Quiz (End of Day)

**Instructions:** Choose the best answer for each question.

1.  Which loop is best when you know the exact number of iterations?
    a) `while`
    b) `do-while`
    c) `for`
    d) `foreach`

2.  What are the three parts of a `for` loop's definition, in order?
    a) Condition, Initializer, Iterator
    b) Initializer, Iterator, Condition
    c) Iterator, Condition, Initializer
    d) Initializer, Condition, Iterator

3.  How many times will the following loop print "Hello"?
    `for (int i = 0; i < 5; i++) { ... }`
    a) 4
    b) 5
    c) 6
    d) It will run forever.

4.  Which loop is guaranteed to execute its body at least once?
    a) `for`
    b) `while`
    c) `do-while`
    d) None of the above.

5.  What does the `break` statement do inside a loop?
    a) Skips the current iteration and goes to the next.
    b) Exits the loop immediately.
    c) Pauses the program.
    d) Deletes the loop from memory.

6.  What does the `continue` statement do inside a loop?
    a) Skips the current iteration and goes to the next.
    b) Exits the loop immediately.
    c) Ends the entire program.
    d) Continues to the line after the loop.

7.  What is an "infinite loop"?
    a) A loop that runs more than one million times.
    b) A loop whose condition will never become false.
    c) A loop that contains another loop.
    d) A loop that uses the `break` statement.

8.  What will be the output of this code?
    ```csharp
    int i = 5;
    while (i > 0) { Console.Write(i); i--; }
    ```
    a) `54321`
    b) `543210`
    c) `43210`
    d) `4321`

9.  What is the final value of `count` after this loop?
    ```csharp
    int count = 0;
    for (int i = 1; i <= 3; i++) { count += i; }
    ```
    a) 3
    b) 5
    c) 6
    d) 7

10. A loop inside of another loop is called a...
    a) Super loop
    b) Nested loop
    c) Complex loop
    d) Sub-loop

11. What is wrong with this `while` loop?
    ```csharp
    int x = 1;
    while (x <= 10) { Console.WriteLine(x); }
    ```
    a) The condition is invalid.
    b) The variable `x` is never updated, causing an infinite loop.
    c) `WriteLine` cannot be used inside a loop.
    d) Nothing is wrong.

12. In a `do-while` loop, the condition is checked...
    a) Before the loop body executes.
    b) After the loop body executes.
    c) During each line of the loop body.
    d) Only when a `break` statement is found.

13. What is the output of this code?
    ```csharp
    for (int i = 1; i < 5; i++) { if (i == 3) continue; Console.Write(i); }
    ```    a) `124`
    b) `1234`
    c) `12`
    d) `1245`

14. The `i++` part of a `for` loop is called the...
    a) Initializer
    b) Terminator
    c) Iterator
    d) Conditioner

15. What is the output of this code?
    ```csharp
    for (int i = 0; i < 3; i++) { for (int j = 0; j < 2; j++) { Console.Write("*"); } }
    ```
    a) `**`
    b) `***`
    c) `******`
    d) `*********`

16. Which loop is most suitable for creating an interactive menu that always displays at least once?
    a) `for`
    b) `while`
    c) `do-while`

17. If you start a `for` loop with `for (int i = 10; i > 0; i--)`, the loop will...
    a) Count up from 1 to 10.
    b) Count down from 10 to 1.
    c) Cause a syntax error.
    d) Run infinitely.

18. What is the output of this code?
    ```csharp
    for (int i = 1; i < 10; i++) { if (i == 4) break; Console.Write(i); }
    ```
    a) `1234`
    b) `123`
    c) `12`
    d) `12356789`

19. A `while(true)` loop is...
    a) Always an error.
    b) An infinite loop that must use an internal `break` statement to exit.
    c) A loop that runs only once.
    d) A loop that runs as long as the computer is on.

20. In WPF, programmatically creating multiple UI elements is a great use case for a...
    a) `switch` statement
    b) `if-else` statement
    c) Loop
    d) Variable declaration

---
<details>
  <summary><strong>ANSWER KEY</strong></summary>
  
  1. **c)** `for`
  2. **d)** Initializer, Condition, Iterator
  3. **b)** 5 (for i = 0, 1, 2, 3, 4)
  4. **c)** `do-while`
  5. **b)** Exits the loop immediately.
  6. **a)** Skips the current iteration and goes to the next.
  7. **b)** A loop whose condition will never become false.
  8. **a)** `54321`
  9. **c)** 6 (1 + 2 + 3)
  10. **b)** Nested loop
  11. **b)** The variable `x` is never updated, causing an infinite loop.
  12. **b)** After the loop body executes.
  13. **a)** `124` (it skips printing 3)
  14. **c)** Iterator
  15. **c)** `******` (The outer loop runs 3 times, the inner loop runs 2 times each time, 3*2=6)
  16. **c)** `do-while`
  17. **b)** Count down from 10 to 1.
  18. **b)** `123` (it breaks when i becomes 4)
  19. **b)** An infinite loop that must use an internal `break` statement to exit.
  20. **c)** Loop
</details>
