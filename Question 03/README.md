# AWT Calculator Program (`Q03_Calculator`)

A Java desktop application that implements a fully functional standard calculator using Abstract Window Toolkit (AWT) graphical controls and event handling.

## Why These Imports Are Used

The program relies on standard AWT packages to construct the user interface layout, render interactive controls, and manage user actions:

* **`java.awt.*`**: Imports the Abstract Window Toolkit package containing classes for designing GUI windows and components:
* `Frame`: Provides the main application window frame container.
* `TextField`: Implements the screen display text box at the top of the calculator.
* `Panel`: Acts as a container component to group and organize the keypad buttons.
* `GridLayout`: Arranges calculator buttons in a uniform 5-row by 4-column grid layout with spacing.
* `Button`: Creates clickable push buttons for numbers, operations, and control functions.
* `Color` and `Font`: Configures background shades and typography styles.
* `BorderLayout`: Manages the component positioning, placing the display at the `NORTH` and the button panel in the `CENTER`.


* **`java.awt.event.*`**: Provides event-handling classes and interfaces for user interactions:
* `ActionListener`: Implemented by the class to listen for button clicks (`actionPerformed`).
* `ActionEvent`: Carries metadata about which button command was triggered.
* `WindowAdapter` and `WindowEvent`: Captures window closing events to safely dispose of the application window upon exit.



## How the Code Works

1. **Window Setup & Layout**:
* Extends the AWT `Frame` class and sets its title to `"AWT Calculator"`.
* Configures a read-only `TextField` display initialized to `"0"` at the top (`NORTH`).
* Creates a 5x4 grid `Panel` populated with calculator keys (`"C"`, `"<"`, `"%"`, `"/"`, numbers, operators, decimal, and equals sign).
* Registers an `ActionListener` on each individual button so clicks are routed back to the main class.


2. **Event Handling (`actionPerformed`)**:
* **Digit Input (`[0-9]`)**: Appends digits to the display string or overwrites the initial `"0"` / new entry state (`startNew`).
* **Decimal Point (`.`)**: Appends a decimal point if one doesn't already exist in the current number entry.
* **Clear (`C`)**: Resets the accumulator (`acc`), clears operators, and resets the display to `"0"`.
* **Backspace (`<`)**: Removes the last typed character from the display field.
* **Sign Toggle (`+/-`)**: Toggles positive/negative signs on the current number entry.
* **Percentage (`%`)**: Converts the current display value into its percentage equivalent.
* **Arithmetic Operators (`+`, `-`, `*`, `/`)**: Stores the active operator and handles expression chaining if multiple operators are pressed sequentially.
* **Equals (`=`)**: Evaluates the accumulated expression using `calc()`, handles division-by-zero safeguards (`Double.NaN`), and displays the final result.


3. **Calculation Engine (`calc`)**: Evaluates basic arithmetic operations (`+`, `-`, `*`, `/`) between the accumulator value and the current input value, returning `Double.NaN` if a division by zero is attempted.
4. **Display Formatting (`show`)**: Automatically formats numeric outputs by stripping unnecessary trailing decimal zeros (casting to `long` when whole numbers are present) for cleaner readability.
