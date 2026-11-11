# TCP Client-Server Programs (`Q04_TCPClient` & `Q04_TCPServer`)

A Java network programming example demonstrating client-server communication using TCP (Transmission Control Protocol) sockets for reliable, connection-oriented data exchange.

## Why These Imports Are Used

Both programs rely on core networking and I/O packages to establish connections, listen on ports, and stream text back and forth:

* **`java.io.*`**: Imports Input/Output stream classes required for reading and writing data across the network connection:
* `BufferedReader` & `InputStreamReader`: Reads incoming text streams line-by-line from the socket input stream.
* `PrintWriter`: Writes text data to the socket output stream, with auto-flushing enabled (`true`) to ensure messages are sent immediately without being trapped in memory buffers.
* `IOException`: Handles checked exceptions that occur during network failures, port binding conflicts, or unexpected disconnections.


* **`java.net.*`**: Imports networking classes required for socket communication:
* `Socket`: Represents the endpoint for network communication used by the client to connect to the server, and created by the server upon accepting a client connection.
* `ServerSocket`: Waits for incoming client connection requests on a specified port number.



---

## How the Code Works

### 1. TCP Server (`Q04_TCPServer`)

* **Port Binding & Listening**: Initializes a `ServerSocket` bound to port `5000` and enters a listening state (`serverSocket.accept()`), waiting for a client connection.
* **Connection Acceptance**: Once a client connects, it establishes a dedicated communication `Socket` and logs `"Client connected."`.
* **Data Reception & Response**:
* Wraps the socket's input stream in a `BufferedReader` to read the incoming text message sent by the client (`input.readLine()`).
* Prints the received message to the console.
* Uses a `PrintWriter` to send an acknowledgment response back to the client (`output.println(...)`).


* **Resource Management**: Uses a Java **try-with-resources** block, which automatically closes the server socket, client socket, and streams when execution finishes or if an exception occurs.

### 2. TCP Client (`Q04_TCPClient`)

* **Connection Initiation**: Attempts to connect to the server running on `localhost` (IP `127.0.0.1`) at port `5000` using a `Socket` object.
* **Message Transmission**:
* Creates a `PrintWriter` linked to the socket's output stream and sends a greeting message (`"Hello Server, this is the client."`).


* **Reading Server Response**:
* Wraps the socket input stream in a `BufferedReader` to wait for and read the reply sent back by the server.
* Prints the server's response to the console.


* **Exception Handling**: Catches any `IOException` (such as a `ConnectException` if the server is offline) and prints an error message.
