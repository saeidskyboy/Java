# Setting up Java Development in VS Code (macOS)

This guide walks you through the initial steps to set up a Java development environment using Visual Studio Code on macOS. This is perfect for starting to learn Java and practicing coding.


## Steps

### 1. Install the Java Development Kit (JDK)

The JDK is essential for compiling and running Java code.

1.  **Download and Install JDK:**
    * Download the latest JDK from a reliable source like [Oracle JDK](https://www.oracle.com/java/technologies/downloads/) or [Eclipse Temurin](https://adoptium.net/).
    * Download a JDK version 17 or later, as these versions are well-supported and have modern features.
    * Run the downloaded installer and follow the prompts.

2.  **Set `JAVA_HOME` and Update `PATH`:**
    This step allows your system and tools like VS Code to easily find your Java installation.

    * Open the **Terminal** application.
    * Find the path to your installed JDK by running:
        ```bash
        /usr/libexec/java_home
        ```
        Copy the output path (e.g., `/Library/Java/JavaVirtualMachines/jdk-17.jdk/Contents/Home`).
    * Open your shell profile file for editing. This is typically `.zshrc` (for newer macOS) or `.bash_profile` (for older macOS or if you manually switched).
        ```bash
        # For zsh (default on recent macOS):
        nano ~/.zshrc

        # For bash:
        # nano ~/.bash_profile
        # or
        # nano ~/.bashrc
        ```
    * Add the following lines to the *end* of the file:
        ```bash
        # Set JAVA_HOME dynamically
        export JAVA_HOME=$(/usr/libexec/java_home)

        # Add JDK's bin directory to the PATH
        export PATH="$JAVA_HOME/bin:$PATH"
        ```
    * Save the file and exit the editor (`Ctrl + X`, then `Y`, then `Enter` in nano).
    * Apply the changes by sourcing the file in your *current* terminal session:
        ```bash
        # For zsh:
        source ~/.zshrc

        # For bash:
        # source ~/.bash_profile
        # or
        # source ~/.bashrc
        ```
    * **Verify:** Open a *new* Terminal window and run:
        ```bash
        java -version
        javac -version
        echo $JAVA_HOME
        ```
        You should see the version information and the JDK path printed.


### 2. Install Essential VS Code Extensions for Java

VS Code needs extensions to provide rich Java language features.

1.  Open VS Code.
2.  Go to the Extensions view by clicking the square icon on the sidebar or pressing `Ctrl+Shift+X` (or `Cmd+Shift+X`).
3.  Search for **"Extension Pack for Java"**.
4.  Click the **Install** button for the extension pack published by Microsoft. This pack includes several useful extensions automatically.

### 3. Create Your First Java Project

You can create a project with or without build tools.

#### Option A: No Build Tools (Simple Start)

1.  Open the **Command Palette** (`Ctrl+Shift+P` or `Cmd+Shift+P`).
2.  Type "Create Java Project" and select the command.
3.  Choose the "**No Build Tools**" option.
4.  Select a location on your computer for the project folder.
5.  Enter a name for your project (e.g., `MyFirstJavaProject`). VS Code will set up a basic structure.

#### Option B: Maven (Recommended for Larger Projects)

1.  Open the **Command Palette** (`Ctrl+Shift+P` or `Cmd+Shift+P`).
2.  Type "Create Java Project" and select the command.
3.  Choose the "**Maven**" option.
4.  Follow the prompts to select a Maven archetype (e.g., `maven-archetype-quickstart`) and provide details like `groupId` and `artifactId`.
5.  Select a location for the project.

### 4. Write and Run Your First Java Program

Let's create a simple "Hello, World!" program.

1.  In the VS Code Explorer view (`Ctrl+Shift+E` or `Cmd+Shift+E`), navigate to the source folder:
    * For "No Build Tools": Look for the `src` folder.
    * For Maven: Look for `src/main/java`.
2.  Create a new Java file (e.g., `HelloWorld.java`) inside the source folder (or within a package folder if you created one).
3.  Add the following code to the file:
    ```java
    public class HelloWorld {
        public static void main(String[] args) {
            System.out.println("Hello, Java!");
        }
    }
    ```
4.  You should see "Run" and "Debug" code lenses appear above the `main` method. Click **Run**.
5.  Alternatively, right-click anywhere in the code editor and select "Run Java".
6.  The output "Hello, Java!" will appear in the VS Code terminal panel.

### 5. Popular Java Libraries for Learning

As you progress, you might find these libraries useful for different tasks:

* **JUnit:** A widely used framework for writing unit tests. (Often included or easily added in Maven/Gradle projects).
* **SLF4j & Logback:** Standard libraries for logging messages in your application.
* **Jackson / Gson:** Libraries for easily converting Java objects to/from JSON format.
* **Apache Commons Utilities:** Collections of useful utility classes for various programming tasks (e.g., `commons-lang3`, `commons-collections4`).

## Getting Started

Now you have the basic setup! You can start writing more Java code in your project, experimenting with different language features, and building small programs.

---