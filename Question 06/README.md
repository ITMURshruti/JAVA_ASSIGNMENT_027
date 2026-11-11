# Java RMI Calculator Program (`Calculator`, `CalculatorImpl`, `CalculatorServer`, `CalculatorClient`)

A Java distributed application demonstrating Remote Method Invocation (RMI), allowing a client machine to invoke addition, subtraction, and multiplication methods hosted on a remote server.

## Why These Imports Are Used

The program relies entirely on the `java.rmi` package and its sub-packages to manage distributed object communication:

* **`java.rmi.Remote`**: A marker interface that identifies interfaces whose methods can be invoked from a non-local virtual machine. Any remote service interface must extend this.
* **`java.rmi.RemoteException`**: A checked exception thrown by remote method invocations to signal network failures, communication errors, or server unresponsiveness.
* **`java.rmi.server.UnicastRemoteObject`**: Provides basic remote object functionality, exporting the object so it can listen for incoming remote method calls over TCP sockets.
* **`java.rmi.registry.LocateRegistry`**: Used to bootstrap or locate the RMI registry (`LocateRegistry.createRegistry()` starts a registry on port 1099, and `LocateRegistry.getRegistry()` finds a running registry).
* **`java.rmi.registry.Registry`**: Represents the remote object registry lookup service where remote objects are bound to names and retrieved by clients.

---

## How the Code Works

1. **Defining the Remote Contract (`Calculator`)**:
* Declares the remote methods (`add`, `subtract`, `multiply`) that clients can invoke. Each method explicitly declares that it throws `RemoteException` to handle network issues.


2. **Implementing the Service (`CalculatorImpl`)**:
* Extends `UnicastRemoteObject` and implements the `Calculator` interface.
* Houses the actual business logic for addition, subtraction, and multiplication.


3. **Hosting on the Server (`CalculatorServer`)**:
* Instantiates the remote calculator object (`CalculatorImpl`).
* Starts an RMI registry on port `1099` using `LocateRegistry.createRegistry()`.
* Binds the service instance to a lookup name (`"CalculatorService"`) using `registry.rebind()`.


4. **Invoking Remotely from the Client (`CalculatorClient`)**:
* Locates the RMI registry running on the host server (`localhost` at port `1099`).
* Looks up the remote service stub using `registry.lookup("CalculatorService")` and casts it to the `Calculator` interface.
* Executes remote calculations seamlessly as if they were local method calls and prints the output.
