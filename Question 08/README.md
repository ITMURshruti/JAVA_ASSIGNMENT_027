# JDBC Applet Form Registration Program (`Q08_AppletJDBC`)

A Java application combining an AWT/Applet graphical form interface with JDBC (Java Database Connectivity) to securely capture and store user credentials (name and password) into a relational database.

## Why These Imports Are Used

The program relies on standard GUI components, event handling libraries, and the `java.sql` package to connect to databases and execute queries:

* **`java.applet.Applet` & `java.awt.***`: Provides UI container components (`Applet`, `Label`, `TextField`, `Button`) and layout managers (`GridLayout`) to construct the visual user registration form.
* **`java.awt.event.*`**: Captures user interface interactions via `ActionListener` and `ActionEvent` when the submit button is clicked.
* **`java.sql.Connection`**: Manages the active session and communication channel with the target relational database.
* **`java.sql.DriverManager`**: Acts as the management framework for establishing connections to database drivers based on connection URLs.
* **`java.sql.PreparedStatement`**: Pre-compiles SQL insertion queries with parameters (`?`), preventing SQL injection vulnerabilities and optimizing execution speed.
* **`java.sql.SQLException`**: Handles database-related errors such as connection failures, syntax errors, or constraint violations.

---

## How the Code Works

1. **Form Layout Initialization (`init`)**:
* Sets up a grid layout containing text labels, input text fields for the username and password (with masked password characters), a submission button, and a status feedback label.


2. **Event Capture & Validation (`actionPerformed`)**:
* Triggers when the user clicks the submit button, extracting input strings from both text fields and checking that neither field is empty.


3. **Database Connectivity & Execution**:
* **Driver Loading**: Loads the database driver using `Class.forName()`.
* **Connection Establishment**: Connects to the database server using `DriverManager.getConnection()` with the specified database URL, username, and password credentials.
* **Parameterized Query Execution**: Prepares an SQL `INSERT` statement (`PreparedStatement`), securely binds the user input variables, and executes the update (`executeUpdate()`).


4. **Status Feedback**:
* Displays a success or error message on the applet interface based on whether the database transaction completed successfully.
