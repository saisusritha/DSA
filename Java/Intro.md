
---

# 📘 Introduction to Java

---

## 1️⃣ History of Java

* Java was created by **James Gosling** at **Sun Microsystems** in **1995**.
* Initially named **Oak** (after a tree 🌳 near Gosling’s office), later renamed **Java** ☕ because Oak was already trademarked.
* Purpose: to create a programming language that is:

  * **Simple**: Syntax similar to C++, but safer and easier to read
  * **Object-Oriented**: Supports concepts like classes, objects, encapsulation, inheritance, polymorphism, and abstraction
  * **Platform Independent**: Write Once, Run Anywhere (WORA) → you can write a program on Windows and run it on Mac or Linux without changes
* Quickly became popular for **enterprise applications, web apps, mobile apps (especially Android), embedded systems, and large-scale distributed systems**

💡 **Fun fact:** Java was intended to be used in set-top boxes and TV devices! 📺

---

## 2️⃣ Features of Java

| Feature                         | Explanation                                                                                                                                                  |
| ------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| **Object-Oriented**             | Most things in Java are objects (classes and objects). Primitives like `int`, `double`, `boolean` are NOT objects. This allows reusability and modular code. |
| **Platform Independent**        | Java code is compiled to **bytecode**, which can run on any device with a **Java Virtual Machine (JVM)**.                                                    |
| **Robust**                      | Java provides strong memory management, exception handling, and compile-time type checking to reduce runtime errors.                                         |
| **Secure**                      | Java programs run inside a sandbox environment, preventing malicious code from affecting the host system.                                                    |
| **Multithreaded**               | Java supports multiple threads (concurrent execution) natively, making it ideal for modern applications.                                                     |
| **Dynamic**                     | Java programs can load classes at runtime, allowing dynamic updates and modular programming.                                                                 |
| **Automatic Memory Management** | Java has a **Garbage Collector (GC)** that automatically frees memory occupied by unused objects.                                                            |
| **High Performance**            | Java uses **Just-In-Time (JIT) compilation** to convert bytecode into native machine code for faster execution.                                              |
| **Rich API & Libraries**        | Java has built-in support for data structures, networking, I/O, graphics, concurrency, and more.                                                             |

---

## 3️⃣ Java Program Structure

```java
// File: HelloWorld.java
public class HelloWorld {

    public static void main(String[] args) {
        // Print to console
        String greeting = "Hello, Java! 👋";
        System.out.println(greeting);

        // Call another method
        printMessage("Learning Java is fun! 🚀");
    }

    // Method declaration
    public static void printMessage(String message) {
        System.out.println(message);
    }
}
```

### Explanation of Every Line

1. **`// File: HelloWorld.java`** → comment for humans; ignored by compiler
2. **`public class HelloWorld`** → declares a class named `HelloWorld`.

   * **Class = blueprint** for objects
   * **Filename must match class name**
3. **`public static void main(String[] args)`** → entry point of the program

   * `public` → accessible from anywhere
   * `static` → can be run without creating an object
   * `void` → does not return any value
   * `String[] args` → command-line arguments
4. **`String greeting = "Hello, Java! 👋";`** → declares a string variable and assigns value
5. **`System.out.println(greeting);`** → prints text to console
6. **`printMessage("Learning Java is fun! 🚀");`** → calls a **static method** in the same class
7. **`public static void printMessage(String message)`** → method declaration
8. **`System.out.println(message);`** → prints the passed message

💡 Analogy:

* **Class** = cookbook
* **Main method** = main dish
* **Other methods** = side dishes 🍲

---

## 4️⃣ Naming Conventions

* **Class names** → `PascalCase` (`HelloWorld`)
* **Method & variable names** → `lowerCamelCase` (`printMessage`)
* **Constants** → `UPPERCASE_WITH_UNDERSCORES` (`PI = 3.14`)

💡 Following conventions makes your code readable and maintainable, especially in teams.

---

## 5️⃣ Static Keyword

* **Static variables** → shared among all objects of the class
* **Static methods** → can be called without creating an object
* **Static blocks** → executed once when the class is loaded

Example:

```java
public class Counter {
    static int count = 0;

    public Counter() {
        count++;
    }
}
```

* Every new `Counter` object increases the **same** `count` variable.

💡 Analogy: Static = **shared notice board** 📝

---

## 6️⃣ Garbage Collector (GC) & Memory Management

* **Automatic memory management** → no need to manually free memory
* **Prevents dangling references** (references pointing to deleted memory) and **memory leaks** (memory never freed)

### Example of Memory Leak

```java
private static List<Integer> list = new ArrayList<>();
```

* If you keep adding elements and never remove them, memory fills up.

### Dangling Reference Example

```java
String str = new String("Hello");
String ref = str;
str = null; // still reachable via ref, not collected
```

### GC Phases

1. **Mark** → finds objects no longer referenced
2. **Sweep** → deletes them from memory
3. **Compact** → reduces memory fragmentation

💡 Think of GC as a **friendly janitor robot** 🧹🤖

---

## 7️⃣ How Java Code Runs

1. **Write Code** → `.java` file
2. **Compile** → `javac HelloWorld.java` → `.class` bytecode
3. **Execute** → `java HelloWorld` → JVM runs bytecode

### Components

| Component                          | Function                               |
| ---------------------------------- | -------------------------------------- |
| **JDK (Java Development Kit)**     | Compiler + JVM + tools for development |
| **JRE (Java Runtime Environment)** | JVM + libraries for running code       |
| **JVM (Java Virtual Machine)**     | Executes bytecode on your platform     |

💡 JVM acts as an **interpreter between bytecode and your OS** 🖥️

---

## 8️⃣ Why Learn Java Before Coding

* Strongly typed → catches errors at compile-time
* Encourages object-oriented programming → clean and reusable code
* Huge community & rich libraries → easy to learn and implement
* Useful for **DSA, competitive programming, backend development, Android apps**

---

✅ This version is **fully detailed, accurate, and beginner-friendly**. It explains:

* Every line in a basic program
* Static, main method, variables, methods
* Garbage collection & memory concepts
* Java program execution, JDK/JRE/JVM
* Naming conventions, history, and features

---

