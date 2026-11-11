# Applet Login Form Program (`Q11_LoginForm`)

A Java Applet program that constructs a graphical user interface form featuring input fields for a user's name and a password.

## Why These Imports Are Used

The program relies on standard Applet, Abstract Window Toolkit (AWT), and event-handling packages to build the form layout and manage user interactions:

* **`java.applet.Applet`**: Provides the core container class required to run Java applets within web browsers or applet viewer environments, handling initialization and lifecycle hooks.
* **`java.awt.*`**: Imports Abstract Window Toolkit components and layout managers for UI design:
* `Label`: Displays static descriptions next to the input boxes (e.g., "Name:" and "Password:").
* `TextField`: Creates single-line text entry components (with character masking enabled via `setEchoChar('*')` for the password field).
* `Button`: Creates a clickable submission control.
* `GridLayout`: Organizes form components in a structured grid arrangement.


* **`java.awt.event.*`**: Captures user interface actions:
* `ActionListener` & `ActionEvent`: Listens for click events on the submission button so user entries can be validated or processed.



## How the Code Works

1. **Layout Initialization (`init`)**:
* Sets up the applet using a `GridLayout` to neatly organize labels, text fields, and buttons into rows and columns.


2. **Component Instantiation**:
* Creates a text field for the user's name.
* Creates a password text field configured with an echo character (`*`) to securely mask sensitive text on the screen.
* Adds a submit button to trigger form actions.


3. **Event Handling (`actionPerformed`)**:
* Registers an `ActionListener` on the submit button to capture clicks and retrieve input values (`getText()`) from both fields for processing or validation.
