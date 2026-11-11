# CRUD Applet Form Program (`Q12_AppletCRUD`)

A Java Applet application that extends the user form interface to perform full **CRUD (Create, Read, Update, Delete)** database operations using JDBC (Java Database Connectivity).

## Why These Imports Are Used

The program relies on GUI layout classes, event-handling interfaces, and database connectivity packages to manage user interactions and execute SQL data operations:

* **`java.applet.Applet` & `java.awt.***`: Provides the UI components (`Applet`, `Label`, `TextField`, `Button`, `TextArea`) and layout managers (`GridLayout`, `BorderLayout`) to construct the interactive form and data display view.
* **`java.awt.event.*`**: Captures user interface actions via `ActionListener` and `ActionEvent` when different operation buttons (Insert, Select, Update, Delete) are clicked.
* **`java.sql.Connection`**: Manages the active session and communication channel with the target relational database server.
* **`java.sql.DriverManager`**: Acts as the management framework for locating and establishing database connections using connection strings and credentials.
* **`java.sql.PreparedStatement`**: Pre-compiles SQL statements with parameter placeholders (`?`), ensuring secure execution of dynamic queries and preventing SQL injection.
* **`java.sql.ResultSet`**: Stores and iterates through tabular data returned by database `SELECT` queries.
* **`java.sql.SQLException`**: Handles database-related errors such as connection timeouts, missing records, or constraint violations.

---

## How the Code Works

1. **Extended Form Layout (`init`)**:
* Reuses the username and password text fields from the previous form while adding dedicated control buttons for each CRUD operation (**Insert/Create**, **View/Read**, **Update**, and **Delete**).
* Includes a feedback status label or text area to display query results and transaction outcomes.


2. **Event Capture & Operation Routing (`actionPerformed`)**:
* Listens for button clicks and determines which database action was requested based on the button command.


3. **Database CRUD Logic**:
* **Create (Insert)**: Prepares and executes an `INSERT` statement to add a new user record into the database table.
* **Read (Select)**: Queries the database using a `SELECT` statement filtered by the entered username, retrieving matching data into a `ResultSet` to display details on the screen.
* **Update**: Executes an `UPDATE` statement to modify existing records (such as changing the password associated with a specific username).
* **Delete**: Executes a `DELETE` statement to remove the specified user record from the database table.


4. **Feedback & Exception Management**:
* Captures transaction success or failure states and updates the user interface accordingly, wrapping all database calls in `try-catch` blocks to handle `SQLException` safely.
