# String Animation Applet Program (`Q02_AnimateString`)

A Java program that demonstrates multithreading and GUI animation by moving a text string horizontally across an Applet window (with standalone frame execution support).

## Why These Imports Are Used

The program relies on standard Abstract Window Toolkit (AWT), Applet, and event-handling packages to build the graphical interface and control lifecycle events:

* **`java.applet.Applet`**: Provides the base container class for running Java applets inside web browsers or older applet viewers. It manages core lifecycle methods like `init()`, `start()`, and `stop()`.
* **`java.awt.*`**: Imports the Abstract Window Toolkit package containing classes for building user interfaces and graphics, specifically:
* `Color` and `Font`: Used to style the visual text presentation (black background, green monospaced text).
* `Graphics`: Provides drawing contexts to render strings and shape rectangles (`fillRect`, `drawString`).
* `Frame`: Used in the `main` method to host and run the applet as a standalone desktop window application.


* **`java.awt.event.*`**: Provides event-handling interfaces and adapter classes, specifically `WindowAdapter` and `WindowEvent`, used to capture window-closing actions (`windowClosing`) so the application exits cleanly when the frame is closed.

## How the Code Works

1. **Initialization (`init`)**: Sets the initial visual appearance of the applet, configuring a black background, green foreground color, and a bold monospaced font.
2. **Thread Lifecycle Management (`start`, `stop`)**:
* The `start()` method initializes and launches a new execution thread (`t = new Thread(this)`), setting the `running` flag to true.
* The `stop()` method flips `running` to false to safely terminate the animation loop.


3. **Multithreaded Animation Loop (`run`)**:
* Runs continuously while `running` is active.
* Increments the horizontal position coordinate `x` by 5 pixels on each iteration.
* Checks if the text has scrolled completely off the screen; if so, wraps it back to the left side (`x = -w`).
* Triggers a screen refresh via `repaint()` and pauses execution for 50 milliseconds using `Thread.sleep(50)` to control the animation frame rate.


4. **Rendering (`paint`, `update`)**:
* Clears the background rectangle and draws the message string `msg` at the updated horizontal coordinate `x` centered vertically within the container.
* Overrides `update()` to call `paint()` directly, reducing screen flicker during rapid frame updates.


5. **Standalone Execution (`main`)**: Creates a native AWT `Frame` container window, embeds the applet, starts its lifecycle methods, and adds a window listener to handle proper shutdown behavior.
