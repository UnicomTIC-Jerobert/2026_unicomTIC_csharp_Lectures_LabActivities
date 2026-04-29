## 💻 Lab Activities (6 Hours) - Student Roster Project

### **Objective**
To design and build a data management application by selecting the appropriate collections for different tasks and using LINQ to perform complex data queries and manipulations.

### **Part 1: The Console Logic Core (Activities 1-7)**

#### **Activity 1 (~30 mins): Defining the `Student` Model**
*   **Concept:** Creating the core data object for the application.
*   **Task:** Create a new Console App `Day15_StudentRoster_Console`.
    1.  Create a `Student.cs` class file.
    2.  Add the following public properties:
        *   `StudentID` (int)
        *   `FirstName` (string)
        *   `LastName` (string)
        *   `Major` (string)
        *   `GPA` (double)
    3.  Create a constructor that accepts all five properties to initialize a new `Student` object.
    4.  `override` the `ToString()` method to return a nicely formatted string, e.g., `"[101] Smith, John - Major: Computer Science, GPA: 3.8"`.

#### **Activity 2 (~35 mins): Creating the `StudentRepository` Class**
*   **Concept:** Encapsulating data storage and management logic.
*   **Task:** Create a `StudentRepository.cs` class.
    1.  Add the following private fields inside the class:
        *   `private List<Student> _students = new List<Student>();`
        *   `private Dictionary<int, Student> _studentDictionary = new Dictionary<int, Student>();`
    2.  Create a constructor. Inside the constructor, call a helper method `private void LoadInitialData()` to populate the collections with 5-7 sample `Student` objects. (Make sure each student has a unique ID).
    3.  Create a public method `public List<Student> GetAllStudents()` that simply returns the `_students` list.

#### **Activity 3 (~35 mins): Add and Remove Logic**
*   **Concept:** Keeping multiple collections in sync.
*   **Task:** In your `StudentRepository.cs`:
    1.  Create a `public void AddStudent(Student newStudent)` method. This method must:
        *   Check if the `_studentDictionary` already contains the `newStudent.StudentID`. If it does, print an error and do nothing.
        *   If the ID is unique, add the student to **both** the `_students` list and the `_studentDictionary`.
    2.  Create a `public void RemoveStudent(int studentId)` method. This method must:
        *   Find the student to remove using the `_studentDictionary` for a fast lookup.
        *   If found, remove them from **both** the `_studentDictionary` and the `_students` list.

#### **Activity 4 (~35 mins): Fast Lookup Method**
*   **Concept:** Leveraging the dictionary for performance.
*   **Task:** In `StudentRepository.cs`:
    1.  Create a `public Student GetStudentById(int studentId)` method.
    2.  Use `_studentDictionary.TryGetValue()` to find the student.
    3.  If the student is found, `return` the student object.
    4.  If not found, `return null`.

#### **Activity 5 (~40 mins): Basic LINQ Queries**
*   **Concept:** Implementing query methods using LINQ.
*   **Task:** In `StudentRepository.cs`, add the following methods:
    1.  `public List<Student> GetStudentsByMajor(string major)`: Use `.Where()` to find all students matching the major.
    2.  `public List<Student> GetAllHonorsStudents()`: Use `.Where()` to find all students with a `GPA >= 3.5`.
    3.  `public double GetAverageGpa()`: Use the LINQ `.Average()` method on the collection of student GPAs.

#### **Activity 6 (~35 mins): Advanced LINQ Queries**
*   **Concept:** Chaining multiple LINQ methods for complex queries.
*   **Task:** In `StudentRepository.cs`, add the following methods:
    1.  `public List<Student> GetTopStudentsByMajor(string major, int count)`: This method should chain multiple LINQ methods. It needs to `Where()` by major, then `OrderByDescending()` by GPA, and finally use `.Take(count)` to get only the top `count` students.
    2.  `public List<string> GetUniqueMajors()`: Use `.Select()` to get all the majors, and then chain `.Distinct()` to get only the unique ones.

#### **Activity 7 (~30 mins): Console UI (Test Harness)**
*   **Concept:** Creating a user interface to interact with the repository.
*   **Task:** In `Program.cs`, create a simple text-based menu that allows a user to:
    1.  View all students.
    2.  Add a new student.
    3.  Look up a student by ID.
    4.  Find all students in a specific major.
    5.  See the top 3 students in "Computer Science".
    Your `Main` method should create **one** instance of the `StudentRepository` and then call its public methods based on user input.

---

### **Part 2: The WPF Graphical User Interface (Activities 8-10)**

#### **Activity 8 (~45 mins): WPF UI Design**
*   **Concept:** Designing a data-centric user interface.
*   **Task:** Create `Day15_StudentRoster_WPF`.
    1.  Design a UI with:
        *   A main `ListBox` (`StudentListBox`) to display the roster.
        *   `TextBox`es for adding a new student (`IdTextBox`, `FirstNameTextBox`, etc.) and an "Add Student" `Button`.
        *   A `TextBox` (`MajorFilterTextBox`) and a "Filter by Major" `Button`.
        *   A `Button` to "Show Honors Students Only".
        *   A `Button` to "Reset Filter / Show All".
        *   A `TextBlock` (`StatusTextBlock`) to show results like average GPA.

#### **Activity 9 (~45 mins): Wiring Up the WPF Backend**
*   **Concept:** Connecting the UI to the `StudentRepository`.
*   **Task:** In `MainWindow.xaml.cs`:
    1.  Add your `Student.cs` and `StudentRepository.cs` files to the project.
    2.  Create a private instance: `private StudentRepository studentRepo = new StudentRepository();`.
    3.  Create a helper method `private void RefreshStudentList(List<Student> students)` that clears the `StudentListBox` and populates it with the list provided.
    4.  When the window loads, call `studentRepo.GetAllStudents()` and pass the result to your `RefreshStudentList` method.
    5.  Implement the "Add Student" button. It should create a `new Student`, call `studentRepo.AddStudent()`, and then refresh the list box with all students.

#### **Activity 10 (~30 mins): Implementing the LINQ Filter Buttons**
*   **Concept:** Making the UI drive the LINQ queries.
*   **Task:**
    1.  Implement the "Filter by Major" button. It should get the major from the `TextBox`, call `studentRepo.GetStudentsByMajor()`, and pass the resulting list to `RefreshStudentList`.
    2.  Implement the "Show Honors Students Only" button. It should call `studentRepo.GetAllHonorsStudents()` and refresh the list.
    3.  Implement the "Reset Filter" button. It should call `studentRepo.GetAllStudents()` and refresh the list.
    4.  Finally, perform the **Git Submission** for the day's work.

---
