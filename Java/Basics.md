
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

### 1.4 Bitwise Operators in Java

Bitwise operators work on **binary representations** of integers (`int`, `long`, `short`, `byte`).

| Operator             | Symbol | Description                           | Example                                 |
| -------------------- | ------ | ------------------------------------- | --------------------------------------- |
| AND                  | `&`    | Performs bitwise AND                  | `5 & 3 → 0101 & 0011 = 0001 → 1`        |
| OR                   | `\|`   | Performs bitwise OR                   | `5 \| 3 → 0101 \| 0011 = 0111 → 7`      |
| XOR                  | `^`    | Performs bitwise XOR                  | `5 ^ 3 → 0101 ^ 0011 = 0110 → 6`        |
| NOT                  | `~`    | Bitwise complement                    | `~5 → ~0101 = 1010` (in 32-bit int: -6) |
| Left shift           | `<<`   | Shifts bits to left, fills 0 on right | `5 << 1 → 0101 << 1 = 1010 → 10`        |
| Right shift          | `>>`   | Shifts bits to right, preserves sign  | `5 >> 1 → 0101 >> 1 = 0010 → 2`         |
| Unsigned right shift | `>>>`  | Shifts bits to right, fills 0         | `-5 >>> 1 → shifts with 0 fill`         |

---

### 🔹 Example Code

```java
public class BitwiseExample {
    public static void main(String[] args) {
        int a = 5;  // 0101
        int b = 3;  // 0011

        System.out.println(a & b);  // 1
        System.out.println(a | b);  // 7
        System.out.println(a ^ b);  // 6
        System.out.println(~a);     // -6
        System.out.println(a << 1); // 10
        System.out.println(a >> 1); // 2
        System.out.println(a >>> 1);// 2
    }
}
```

---

💡 **Fun Fact:**
Bitwise operators are super useful for **competitive programming**, **encryption**, and **low-level optimizations**. For example, checking if a number is even or odd can be done with `n & 1`.

---


### 1.5 Assignment Operators

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
### 6. Now we’re diving into **how Java handles numbers and division, including type conversion**. Let’s break it down carefully so it makes sense, and you can add it to your Java `basics.md` file.

---

## 🔹 Division in Java & Type Conversions

### 1️⃣ Integer Division (`int / int`)

* If **both operands are integers**, Java performs **integer division**.
* **Decimal part is truncated**, not rounded.

```java
int a = 7;
int b = 2;
System.out.println(a / b); // Output: 3
```

💡 Reason: Java knows both are integers, so it only keeps the whole number part.

---

### 2️⃣ Floating-Point Division (`float` or `double`)

* If **any operand is a floating-point type**, Java performs **decimal division**.

```java
double a = 7;
double b = 2;
System.out.println(a / b); // Output: 3.5
```

* You can **force a number to be float/double** using **suffixes**:

  * `5f` → float
  * `5d` → double (optional, default for decimals is double)

```java
System.out.println(5f / 2f);  // 2.5 (float division)
System.out.println(5d / 2);   // 2.5 (double division)
```

💡 Tip: Writing `5f` explicitly tells Java, “Hey, treat this as a float.”

---

### 3️⃣ Type Conversion (Casting)

* Sometimes we want **decimal division with integers**.
* Use **casting** to convert one operand to `float` or `double`:

```java
int x = 7, y = 2;
System.out.println((double)x / y); // 3.5
System.out.println((float)x / y);  // 3.5
```

* **Rules:**

  * Java automatically **promotes smaller types** (`byte`, `short`) to `int` in arithmetic operations.
  * Mixed types (`int` + `double`) → result is **promoted to larger type** (`double`).

---

### 4️⃣ Why `5f`, `6f` etc.

* By default, **decimal numbers** like `5.0` are **double**.
* `float` uses **4 bytes**, `double` uses **8 bytes**.
* Adding `f` ensures the number is **stored as float**. Without `f`, Java treats it as double, which can cause **type mismatch errors** in float variables:

```java
float f = 5.0;  // ❌ Error: 5.0 is double
float f2 = 5.0f; // ✅ Correct
```

---

### 5️⃣ Summary Table

| Operands           | Result Type | Example               | Output |
| ------------------ | ----------- | --------------------- | ------ |
| int / int          | int         | 7 / 2                 | 3      |
| int / double       | double      | 7 / 2.0               | 3.5    |
| float / int        | float       | 5f / 2                | 2.5    |
| double / float     | double      | 5.0 / 2f              | 2.5    |
| byte/short in expr | int         | byte b1=5,b2=2; b1/b2 | 2      |

---

## 🔹 Key Takeaways

1. **Division operator `/`** behaves differently depending on types.
2. **Integer division** truncates decimals; **floating-point division** keeps decimals.
3. **`f` and `d` suffixes** control type explicitly (`float` or `double`).
4. **Casting** lets you control the type to get decimal division when needed.
5. Java automatically **promotes smaller types** to avoid errors.

### 7. Let’s expand your Java basics section with **primitive types, their storage, and behavior**, including how integers, floats, doubles, and longs are stored in memory. This will help you understand division, type promotion, and memory efficiency too.

---

# 🔹 Java Primitive Data Types

Java has **8 primitive types**. These are **not objects**, stored directly in memory, and are the building blocks of all Java programs.

| Type      | Size    | Default Value | Example                  | Range / Notes                 |
| --------- | ------- | ------------- | ------------------------ | ----------------------------- |
| `byte`    | 1 byte  | 0             | `byte b = 100;`          | -128 to 127                   |
| `short`   | 2 bytes | 0             | `short s = 1000;`        | -32,768 to 32,767             |
| `int`     | 4 bytes | 0             | `int i = 100000;`        | -2³¹ to 2³¹-1                 |
| `long`    | 8 bytes | 0L            | `long l = 10000000000L;` | -2⁶³ to 2⁶³-1                 |
| `float`   | 4 bytes | 0.0f          | `float f = 5.5f;`        | ~6-7 decimal digits           |
| `double`  | 8 bytes | 0.0d          | `double d = 5.555555;`   | ~15-16 decimal digits         |
| `char`    | 2 bytes | '\u0000'      | `char c = 'A';`          | Unicode characters 0 to 65535 |
| `boolean` | 1 bit   | false         | `boolean flag = true;`   | true / false                  |

---

## 🔹 How Numbers Are Stored

### 1️⃣ **Integers (`byte`, `short`, `int`, `long`)**

* Stored in **binary using two’s complement** for signed numbers.
* Two’s complement allows **positive and negative numbers** with simple addition/subtraction.
* Example:

  * `int x = -5` → Stored as 32-bit binary: `11111111 11111111 11111111 11111011`

💡 Tip: Integer division truncates the decimal part because the CPU uses **binary integer arithmetic** for these types.

---

### 2️⃣ **Floating-Point Numbers (`float`, `double`)**

* Stored using **IEEE 754 standard**:

  * **Sign bit** (1 bit) → positive or negative
  * **Exponent** → scales the number
  * **Mantissa (fraction)** → precision bits

Example: `float f = 5.5f;`

* 4 bytes are split as:

  * 1 bit sign, 8 bits exponent, 23 bits mantissa

* `double` is **8 bytes**: 1 bit sign, 11 bits exponent, 52 bits mantissa → more precision

💡 Tip: Floats are **less precise** than doubles. Use float for memory optimization and double for accuracy.

---

### 3️⃣ **Type Casting & Promotion**

* **Automatic Promotion:** Smaller types are promoted to larger types in expressions to avoid overflow.

  * Example: `byte + byte → int` automatically
* **Explicit Casting:** Needed to convert larger types to smaller types.

  * Example: `(int)5.7 → 5`
* **Division Example:**

  * `int / int → int` (truncates)
  * `(double)int / int → double` (decimal preserved)

---

### 4️⃣ **Long Numbers & Suffix**

* Java assumes integer literals are `int` by default.
* To store larger numbers in `long` → append `L` or `l`:

  ```java
  long bigNum = 10000000000L; // L is required
  ```
* Similarly, floating-point literals are **double by default**. Use `f` for float:

  ```java
  float f = 5.5f;
  ```

---

### 5️⃣ **Boolean**

* True/False → cannot be stored as 0/1 like C. Only `true` or `false`.

### 6️⃣ **Character**

* 2 bytes → stores **Unicode characters**, not ASCII only.
* Allows **international characters** like `char c = 'π';`.

---

### 🔹 Key Takeaways

1. **Memory size matters**: `int` = 4 bytes, `long` = 8 bytes, `float` = 4 bytes, `double` = 8 bytes.
2. **Integer division truncates**, floating-point preserves decimals.
3. **Type promotion and casting** control precision and memory usage.
4. Always use **suffixes** (`f`, `L`) to avoid type mismatches.



---

