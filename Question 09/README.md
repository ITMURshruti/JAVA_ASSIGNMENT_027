# Student Portal Registration Program (`Q09_StudentPortal`)

A Java database application that implements a student registration portal using JDBC (Java Database Connectivity) to store and manage student records in a relational database.

## Why These Imports Are Used

The program relies on standard input/output and JDBC packages to interact with the console and execute SQL database transactions:

* **`java.io.*`**: Imports Input/Output stream classes (`BufferedReader`, `InputStreamReader`) to capture user input entered through the console terminal.
* **`java.sql.Connection`**: Manages the active session and communication channel between the Java application and the database server.
* **`java.sql.DriverManager`**: Serves as the management system to locate and establish connections to the database using the specified connection string credentials.
* **`java.sql.PreparedStatement`**: Pre-compiles SQL queries with parameter placeholders (`?`), preventing SQL injection attacks and ensuring secure data handling.
* **`java.sql.SQLException`**: Handles checked database exceptions such as connection timeouts, duplicate key violations, or invalid query syntax.

---

## How the Code Works

1. **Console Input Setup**:
* Initializes a `BufferedReader` linked to `System.in` to collect student details (such as student ID, name, email, and course) from the administrator or user.


2. **Database Connection Establishment**:
* Loads the JDBC driver and connects to the target database server using `DriverManager.getConnection()`.


3. **Parameterized Statement Execution**:
* Constructs an SQL `INSERT` query statement.
* Securely binds each user-entered field into the `PreparedStatement` parameters to prevent formatting bugs and injection risks.
* Executes the update using `executeUpdate()` to save the record permanently in the database table.


4. **Result Feedback**:
* Captures the success status of the transaction and prints a confirmation message to the console, wrapping execution inside exception-handling blocks to manage connection errors gracefully.
