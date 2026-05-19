
---

# 📚 Java Basics

---

## 1️⃣ Java Operators

### 1.1 Arithmetic Operators

| Operator | Meaning             | Example      |
| -------- | ------------------- | ------------ |
| `+`      | Addition            | `5 + 3 = 8`  |
| `-`      | Subtraction         | `5 - 3 = 2`  |
| `*`      | Multiplication      | `5 * 3 = 15` |
| `/`      | Division            | `10 / 2 = 5` |
| `%`      | Modulus (remainder) | `10 % 3 = 1` |
| `++`     | Increment by 1      | `i++`        |
| `--`     | Decrement by 1      | `i--`        |

💡 **Tip:** `i++` is postfix increment, `++i` is prefix increment – they differ in the order of evaluation.

---

### 1.2 Relational Operators

| Operator | Meaning          | Example         |
| -------- | ---------------- | --------------- |
| `==`     | Equal to         | `5 == 5 → true` |
| `!=`     | Not equal        | `5 != 3 → true` |
| `>`      | Greater than     | `5 > 3 → true`  |
| `<`      | Less than        | `3 < 5 → true`  |
| `>=`     | Greater or equal | `5 >= 5 → true` |
| `<=`     | Less or equal    | `3 <= 5 → true` |

---

### 1.3 Logical Operators

| Operator | Meaning | Example                   |    |        |   |                |
| -------- | ------- | ------------------------- | -- | ------ | - | -------------- |
| `&&`     | AND     | `(true && false) → false` |    |        |   |                |
| `        |         | `                         | OR | `(true |   | false) → true` |
| `!`      | NOT     | `!(true) → false`         |    |        |   |                |

---

### 1.4 Assignment Operators

| Operator | Meaning             | Example              |
| -------- | ------------------- | -------------------- |
| `=`      | Assign              | `x = 5`              |
| `+=`     | Add and assign      | `x += 5 → x = x + 5` |
| `-=`     | Subtract and assign | `x -= 3 → x = x - 3` |
| `*=`     | Multiply and assign | `x *= 2 → x = x * 2` |
| `/=`     | Divide and assign   | `x /= 2 → x = x / 2` |
| `%=`     | Modulus and assign  | `x %= 3 → x = x % 3` |

---

## 2️⃣ Input & Output in Java

### 2.1 Understanding `System.out.println`

* `System` → A **built-in Java class** that provides access to system-level resources.
* `out` → A **static object** of type `PrintStream` inside `System` class. It represents the **standard output stream**, usually the console.
* `println` → A **method** of `PrintStream` class that prints the message and moves the cursor to the **next line**.

Example:

```java
System.out.println("Hello, World!");
```

✅ This prints `Hello, World!` to the console and goes to a new line.

* `System.out.print("Hi");` → prints without moving to a new line
* `System.out.printf("Age: %d", 20);` → prints formatted output

---

### 2.2 Scanner Class (Input)

* Java **does not have built-in console input for primitive types** like C’s `scanf`.
* The **Scanner class** is part of `java.util` package and allows reading input from **keyboard, file, or string**.

```java
import java.util.Scanner; // imports Scanner class

public class InputExample {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in); // creates Scanner object

        System.out.print("Enter your name: ");
        String name = sc.nextLine(); // reads a line of text

        System.out.print("Enter your age: ");
        int age = sc.nextInt(); // reads an integer

        System.out.println("Hello " + name + ", you are " + age + " years old.");
    }
}
```

💡 **Tips:**

* `import java.util.Scanner;` → tells Java where to find the `Scanner` class.
* `Scanner sc = new Scanner(System.in);` → creates a Scanner object to read input from console.
* `nextLine()` → reads a full line of text
* `nextInt()` → reads an integer

---

## 3️⃣ Loops

### 3.1 `for` loop

```java
for(int i = 0; i < 5; i++) {
    System.out.println(i); // prints 0 to 4
}
```

### 3.2 `while` loop

```java
int i = 0;
while(i < 5) {
    System.out.println(i);
    i++;
}
```

### 3.3 `do-while` loop

```java
int i = 0;
do {
    System.out.println(i);
    i++;
} while(i < 5);
```

💡 **Tip:** `do-while` executes **at least once**, unlike `while`.

---

## 4️⃣ Control Statements

### 4.1 `if-else`

```java
int num = 10;
if(num > 0) {
    System.out.println("Positive");
} else if(num < 0) {
    System.out.println("Negative");
} else {
    System.out.println("Zero");
}
```

### 4.2 `switch`

```java
int day = 3;
switch(day) {
    case 1: System.out.println("Monday"); break;
    case 2: System.out.println("Tuesday"); break;
    case 3: System.out.println("Wednesday"); break;
    default: System.out.println("Other day");
}
```

---

## 5️⃣ Functions (Methods) in Java

* **Method = reusable block of code**
* **Syntax**:

```java
returnType methodName(parameters) {
    // code
}
```

### 5.1 Four Types of Functions

| Type                    | Description                       | Example                                                    |
| ----------------------- | --------------------------------- | ---------------------------------------------------------- |
| **No input, No output** | No parameters, does not return    | `void greet() { System.out.println("Hi"); }`               |
| **Input, No output**    | Takes parameters, does not return | `void printSum(int a, int b) { System.out.println(a+b); }` |
| **No input, Output**    | No parameters, returns value      | `int getRandom() { return 42; }`                           |
| **Input, Output**       | Takes parameters, returns value   | `int sum(int a, int b) { return a+b; }`                    |

---

### 5.2 Call by Value vs Call by Reference

* **Call by Value** (Java default for primitives) → a **copy of the value** is passed

```java
void changeValue(int x) {
    x = 100; // changes only local copy
}

int a = 10;
changeValue(a); // a is still 10
```

* **Call by Reference** (objects) → reference to original object is passed

```java
class Point {
    int x;
}
Point p = new Point();
p.x = 5;
void changePoint(Point pt) {
    pt.x = 10;
}
changePoint(p);
System.out.println(p.x); // prints 10
```

💡 **Tip:** Java **always passes by value**, but **object references themselves are passed by value**, which makes it behave like call by reference for objects.

---

✅ This file now covers everything in **one place**:

* Operators
* Input/output & Scanner class explained word by word
* Loops (`for`, `while`, `do-while`)
* Control statements (`if`, `switch`)
* Functions (four types)
* Call by value & call by reference

---

Absolutely! Let’s expand the **functions (methods) section** in your `basics.md` so it’s extremely detailed, beginner-friendly, and shows every nuance of Java methods. I’ll also add examples, rules, and more explanation about parameters, return types, overloading, and scope.

---

## 5️⃣ Functions (Methods) in Java – Expanded

### 5.1 What is a Function (Method)?

A **function (or method in Java)** is a **block of code that performs a specific task** and can be **reused** anywhere in your program.

Benefits of methods:

* **Reusability:** Write once, use multiple times
* **Modularity:** Breaks the program into smaller pieces
* **Readability:** Easier to understand and maintain

---

### 5.2 Syntax of a Method

```java
returnType methodName(parameters) {
    // code to execute
}
```

* **returnType** → type of value the method returns (`int`, `double`, `String`, `void` if nothing is returned)
* **methodName** → name of the method (should follow **naming conventions**, e.g., `camelCase`)
* **parameters** → optional input values passed to the method (can be zero or more)

Example:

```java
int add(int a, int b) {
    return a + b;
}
```

---

### 5.3 Method Types (4 Types)

| Type                    | Input      | Output        | Example                                                    | When to Use                                                      |
| ----------------------- | ---------- | ------------- | ---------------------------------------------------------- | ---------------------------------------------------------------- |
| **No input, No output** | None       | None          | `void greet() { System.out.println("Hello"); }`            | For simple messages or actions                                   |
| **Input, No output**    | Parameters | None          | `void printSum(int a, int b) { System.out.println(a+b); }` | When you want to do something with input but don’t need a result |
| **No input, Output**    | None       | Returns value | `int getRandomNumber() { return 42; }`                     | When you need to get a value but no input is required            |
| **Input, Output**       | Parameters | Returns value | `int sum(int a, int b) { return a+b; }`                    | When you need a value calculated from input                      |

---

### 5.4 Calling a Method

To **execute a method**, you need to **call it** from another method (usually `main`).

```java
public class Example {
    static void greet() {
        System.out.println("Hello, World!");
    }

    public static void main(String[] args) {
        greet(); // calling the method
    }
}
```

💡 **Tip:** `static` means the method belongs to the class, not an object (we’ll discuss `static` in detail in another section).

---

### 5.5 Parameters and Arguments

* **Parameter:** Variable declared in the method definition
* **Argument:** Actual value passed to the method when called

Example:

```java
void printSum(int a, int b) { // a and b are parameters
    System.out.println(a + b);
}

printSum(5, 10); // 5 and 10 are arguments
```

---

### 5.6 Return Statement

* **Purpose:** Sends a value back to the caller
* **Rule:** Method must have a **matching return type**

```java
int multiply(int x, int y) {
    return x * y;
}

int result = multiply(3, 4); // result = 12
```

* Methods with `void` **cannot** return values.

---

### 5.7 Scope of Variables in Methods

* **Local variables:** Declared inside method, only accessible **within that method**
* **Global/Instance variables:** Declared in class, accessible by **all methods of the class**

```java
public class ScopeExample {
    int number = 10; // instance variable

    void printNumber() {
        int local = 5; // local variable
        System.out.println(number); // accessible
        System.out.println(local);  // accessible
    }

    void anotherMethod() {
        // System.out.println(local); // ❌ error, local not accessible here
    }
}
```

---

### 5.8 Call by Value vs Call by Reference (Revisited)

* **Call by Value (Primitives)** → method gets a **copy of the variable**, original remains unchanged

```java
void changeValue(int x) {
    x = 100; // only changes local copy
}

int a = 10;
changeValue(a);
System.out.println(a); // prints 10
```

* **Call by Reference (Objects)** → method gets a **reference to the object**, original can be modified

```java
class Point {
    int x;
}
Point p = new Point();
p.x = 5;
void changePoint(Point pt) {
    pt.x = 10;
}
changePoint(p);
System.out.println(p.x); // prints 10
```

💡 **Note:** Java **always passes by value**, but object references are copied, so **objects appear to be passed by reference**.

---

### 5.9 Method Overloading

* **Definition:** Multiple methods in the same class with **same name but different parameters**
* **Purpose:** Makes code readable and reusable

```java
class Calculator {
    int sum(int a, int b) { return a + b; }
    double sum(double a, double b) { return a + b; }
}

Calculator calc = new Calculator();
System.out.println(calc.sum(2, 3));   // calls int version
System.out.println(calc.sum(2.5, 3.5)); // calls double version
```

---

### 5.10 Recursion

* **Definition:** A method calling **itself**
* **Example:** Factorial

```java
int factorial(int n) {
    if(n == 0) return 1;
    return n * factorial(n-1);
}
```

💡 **Important:** Always have a **base case**, or the recursion will go **infinite and crash**.

---


---

