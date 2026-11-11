# Java Bean Addition Component (`Q10_NumberBean`)

A Java program that implements a reusable JavaBean component encapsulating properties and logic to calculate the sum of two numbers.

## Why These Imports Are Used

The program relies on standard serialization packages required by the Java Bean specification:

* **`java.io.Serializable`**: Implements the `Serializable` interface, which is a mandatory requirement for Java Beans so their state can be saved, restored, or transmitted across networks.

---

## How the Code Works

1. **Encapsulated Properties**:
* Declares private member variables (`num1`, `num2`, and `result`) to keep internal state hidden from direct external modification (encapsulation).


2. **Default No-Argument Constructor**:
* Provides a public zero-argument constructor (`public Q10_NumberBean()`) as required by the JavaBean architecture specification.


3. **Getter and Setter Methods**:
* Exposes public `getNum1()`, `setNum1()`, `getNum2()`, and `setNum2()` methods allowing external classes or builder tools to inspect and modify bean properties safely.


4. **Business Logic (`calculateSum`)**:
* Computes the addition of `num1` and `num2`, stores it in the `result` property, and returns the computed value via a public `getResult()` getter method.
