# Swing Notepad Application (`Q05_Notepad`)

A Java desktop application that replicates core features of a text editor like Notepad using the Swing GUI framework and standard Java input/output libraries.

## Why These Imports Are Used

The program relies on Java Swing components, AWT layout/event classes, and I/O utility streams to build the graphical interface and handle file operations:

* **`javax.swing.*`**: Imports Swing components for building a modern desktop GUI:
* `JFrame`: Provides the main application window frame.
* `JTextArea`: The primary text editing text area component.
* `JScrollPane`: Wraps the text area to automatically add vertical and horizontal scrollbars when text exceeds the viewable area.
* `JMenuBar`, `JMenu`, `JMenuItem`: Constructs the top application menu bar (File, Edit, etc.) and its dropdown action items.
* `JFileChooser`: Opens native system file dialog windows to select files for opening or saving.
* `JOptionPane`: Displays popup dialog boxes for alerts, confirmations, and error messages.


* **`java.awt.*`**: Imports Abstract Window Toolkit layout managers and styles:
* `BorderLayout`: Manages component positioning inside the frame (placing the scroll pane in the center).
* `Font`: Configures the typography style for the text editor.


* **`java.awt.event.*`**: Captures user interactions like action commands and keyboard shortcuts:
* `ActionListener` & `ActionEvent`: Listens for menu item selections (e.g., clicking "Open" or "Save").
* `KeyEvent` & `InputEvent`: Enables accelerator shortcut keys (like Ctrl+S or Ctrl+O).


* **`java.io.*`**: Imports file stream readers and writers (`BufferedReader`, `BufferedWriter`, `FileReader`, `FileWriter`) to read text from and write text to files on disk.

## How the Code Works

1. **GUI Initialization (`JFrame` & Layout)**:
* Sets up the main window frame with a title and default close operation.
* Initializes a `JTextArea` wrapped inside a `JScrollPane` so users can type and scroll through large documents seamlessly.


2. **Menu Bar Construction (`JMenuBar`)**:
* Creates a **File** menu containing standard options: **New**, **Open**, **Save**, and **Exit**.
* Creates an **Edit** menu with utility actions like **Cut**, **Copy**, **Paste**, and **Select All**.
* Attaches keyboard accelerators (e.g., `Ctrl+S` for saving) and registers action listeners to each menu item.


3. **File Operations**:
* **New**: Clears the text area to start a fresh document.
* **Open**: Triggers a `JFileChooser` dialog, reads the selected text file line-by-line using a `BufferedReader`, and populates the text area.
* **Save**: Opens a save file dialog via `JFileChooser` and writes the text area contents to disk using a `BufferedWriter`.


4. **Text Editing Features**:
* Leverages built-in text manipulation methods provided by `JTextArea` (`cut()`, `copy()`, `paste()`, `selectAll()`) for clipboard interactions.


5. **Exception Handling**: Catters `IOException` during file read/write operations and presents error messages using `JOptionPane` if file access fails.
