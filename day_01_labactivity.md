## 💻 Lab Activities (6 Hours)

### **Objective**
By the end of this lab, you will have installed your tools, built and run both a Console and a WPF application, handled user input in both, and pushed your work to a new GitHub repository.

### **Prerequisites**
1.  **Visual Studio 2022:**
    *   Download and run the Visual Studio Installer.
    *   During installation, you **MUST** select the **".NET desktop development"** workload. This includes the templates for Console and WPF apps.
2.  **Git:**
    *   Install Git for your operating system from [git-scm.com](https://git-scm.com).

---

### **Task 1 (2 hrs): Parallel "Hello Worlds"**
In this task, we will create two projects side-by-side to directly compare them.

#### Part A: The Console App
1.  Open Visual Studio 2022.
2.  Click **"Create a new project"**.
3.  Select the **"Console App"** template (make sure it's the one for C#) and click Next.
4.  Name your project `MyConsoleApp` and click Next.
5.  Select the latest .NET framework available (e.g., .NET 8.0) and click **Create**.
6.  You will see a file named `Program.cs`. Replace the existing `Console.WriteLine(...)` line with the following:
    ```csharp
    Console.WriteLine("Hello from the Console!");
    ```
7.  Press the **Green Play Button (▶)** at the top of Visual Studio to build and run your program. A black terminal window should appear with your message.

#### Part B: The WPF App
1.  In Visual Studio, go to the "Solution Explorer" panel (usually on the right). Right-click on your **Solution** (the very top item).
2.  Go to **Add > New Project...**.
3.  This time, select the **"WPF Application"** template (again, for C#) and click Next.
4.  Name this project `MyWpfApp` and click **Create**.
5.  You will now see two projects in your Solution Explorer.
6.  A new window will open showing `MainWindow.xaml`. This is your visual designer.
7.  Open the **Toolbox** (View > Toolbox). Find the **Button** control and drag it onto the middle of the white window in the designer.
8.  Double-click the new button in the designer. This will automatically switch you to the `MainWindow.xaml.cs` C# file and create a method named `Button_Click`.
9.  Inside this new method, add the following line of code:
    ```csharp
    // This using statement might be needed at the top of your file
    using System.Windows; 

    // Inside your Button_Click method
    MessageBox.Show("Hello from WPF!");
    ```
10. To run this project, right-click on the `MyWpfApp` project in the Solution Explorer and select **"Set as Startup Project"**.
11. Press the **Green Play Button (▶)**. A graphical window with a clickable button should appear. Click it to see your message box!

✅ **Goal Check:** You should be able to run both applications (one at a time by setting the startup project) and see their respective "Hello" messages.

---

### **Task 2 (2 hrs): User Input & Variables**
Now let's store and display some user input.

#### Part A: Console App
1.  Set `MyConsoleApp` as your startup project.
2.  Go to `Program.cs` and replace its content with this code, which introduces variables and input:
    ```csharp
    // Ask for the user's name
    Console.WriteLine("Please enter your name:");
    string name = Console.ReadLine();

    // Ask for the user's age
    Console.WriteLine("Please enter your age:");
    string ageInput = Console.ReadLine();
    int age = int.Parse(ageInput); // Convert the string input to an integer

    // Print a formatted profile card
    Console.WriteLine("--- USER PROFILE ---");
    Console.WriteLine($"Name: {name}"); // The $ allows us to embed variables directly
    Console.WriteLine($"Age: {age}");
    Console.WriteLine("--------------------");
    ```
3.  Run the program and follow the prompts in the console.

#### Part B: WPF App
1.  Set `MyWpfApp` as your startup project.
2.  Open `MainWindow.xaml`. We need to add controls to hold our information. Replace the `<Grid>` content with the following XAML:
    ```xml
    <StackPanel Margin="20">
        <Label>Name:</Label>
        <TextBox x:Name="NameTextBox" Margin="0,0,0,10"/>

        <Label>Age:</Label>
        <TextBox x:Name="AgeTextBox" Margin="0,0,0,10"/>
        
        <Button Content="Generate Profile" Width="150" Click="Button_Click"/>
        
        <TextBlock x:Name="ProfileTextBlock" Margin="0,20,0,0" FontSize="16"/>
    </StackPanel>
    ```
    *   `x:Name` is very important - it's how we will access the control from our C# code.
3.  Now open `MainWindow.xaml.cs`. Replace your `Button_Click` method with this logic:
    ```csharp
    private void Button_Click(object sender, RoutedEventArgs e)
    {
        // 1. Get the input from the TextBox controls and store in variables
        string name = NameTextBox.Text;
        string age = AgeTextBox.Text;

        // 2. Format the output string
        string profile = $"Name: {name}\nAge: {age}"; // \n creates a new line

        // 3. Set the content of the TextBlock to display the result
        ProfileTextBlock.Text = profile;
    }
    ```
4.  Run the WPF app. Type in the text boxes and click the button to see the profile appear below.

✅ **Goal Check:** Your console app should ask for input and print a profile. Your WPF app should take input from text boxes and display the same profile within the window when a button is clicked.

---

### **Task 3 (2 hrs): Git & Repository Setup**
Let's save our work professionally.

1.  **Create a GitHub Repository:** Go to [github.com](https://github.com), log in, and click the **"New"** button to create a new repository. Name it something like `CSharp-Bootcamp-Work`. Make it **Public** and click **Create repository**.
2.  **Open a Terminal:** In Visual Studio, go to **View > Terminal**. This opens a command line terminal at the root of your solution directory.
3.  **Initialize Git:** Type the following commands one by one, pressing Enter after each.
    ```bash
    # Initializes an empty Git repository in your project folder
    git init
    
    # Stages all your new files to be committed
    git add .
    
    # Commits your staged files with a message
    git commit -m "Week 1 Day 1: Initial Console and WPF projects"
    ```
4.  **Connect to GitHub:** On your GitHub repository page, copy the URL. Then run these commands in the terminal, replacing `YOUR_REPO_URL` with the one you copied.
    ```bash
    # Links your local repository to the remote one on GitHub
    git remote add origin YOUR_REPO_URL
    
    # Renames the default branch to 'main' (a modern standard)
    git branch -M main
    
    # Pushes your 'main' branch to the 'origin' remote
    git push -u origin main
    ```

