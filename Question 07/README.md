# Applet Login Form Program (`Q07_LoginForm`)

A Java Applet program that creates a graphical user interface form containing input fields for a username and a password.

## Why These Imports Are Used

The program relies on standard Applet, Abstract Window Toolkit (AWT), and event-handling packages to build the form layout and capture user interactions:

* **`java.applet.Applet`**: Provides the base container class for running Java applets inside web browsers or applet viewer environments, managing lifecycle states like initialization.
* **`java.awt.*`**: Imports AWT components and layout managers for UI design:
* `Label`: Renders static text descriptions next to the input fields (e.g., "Username:" and "Password:").
* `TextField`: Creates single-line text entry boxes (with password masking enabled via `setEchoChar('*')`).
* `Button`: Creates a clickable submission button.
* `GridLayout`: Arranges the form components in an orderly grid structure.


* **`java.awt.event.*`**: Captures user interface actions:
* `ActionListener` & `ActionEvent`: Listens for click events on the submit button so input validation or processing can occur.



## How the Code Works

1. **Layout Setup (`init`)**:
* Initializes the applet and sets a `GridLayout` to neatly arrange form labels, text boxes, and buttons in rows and columns.


2. **Component Creation**:
* Instantiates a `Label` and a `TextField` for the user's name.
* Instantiates a `Label` and a `TextField` for the password, setting an echo character (`*`) to mask sensitive characters on screen.
* Creates a submit `Button` to process the form entry.


3. **Event Handling (`actionPerformed`)**:
* Registers an `ActionListener` on the submit button to capture when the user clicks it.
* Retrieves the entered text from both fields (`getText()`) for authentication or processing.
