# Matrix Multiplication Program (`Q01_MatrixMultiplication`)

A Java program that performs matrix multiplication using buffered console input/output streams.

## Why These Imports Are Used

The program relies on classes from the `java.io` package to handle console input efficiently:

* **`java.io.BufferedReader`**: Reads text from a character-input stream, buffering characters to provide efficient reading. It allows us to read whole lines of text using `readLine()`, which is faster and safer than traditional scanner or byte-by-byte approaches.
* **`java.io.InputStreamReader`**: Acts as a bridge between byte streams and character streams. It takes `System.in` (which reads raw bytes from the console keyboard) and decodes those bytes into readable characters so that `BufferedReader` can process them.
* **`java.io.IOException`**: A checked exception that must be declared in the method signature (`throws IOException`) because input/output operations (such as reading from the system console) can potentially fail or throw errors.

## How the Code Works

1. **Initialization**: Sets up a `BufferedReader` linked to `System.in` to accept user input from the terminal.
2. **Dimension Input & Validation**:
* Prompts the user to enter the row and column sizes for Matrix A (`r1`, `c1`) and Matrix B (`r2`, `c2`).
* Checks the matrix multiplication rule: **the number of columns in Matrix A must equal the number of rows in Matrix B ($c_1 == r_2$)**. If the condition fails, the program halts execution immediately.


3. **Matrix Population**:
* Allocates memory for two 2D arrays (`a` and `b`) and a `product` matrix based on the specified dimensions.
* Uses nested `for` loops to prompt and read individual integer elements for both matrices, converting text inputs via `Integer.parseInt(reader.readLine())`.


4. **Multiplication Logic**:
* Utilizes three nested loops ($i$, $j$, $k$) to compute the dot product, accumulating values into the `product` array.


5. **Displaying Results**: Loops through the resulting matrix and prints the elements row by row in a structured grid format.
