
---

# 🧠 What is Time Complexity?

Time Complexity is a **mathematical way to describe how the runtime of an algorithm grows as the input size grows**.

* Input size = `n` (like number of elements in an array)
* Time Complexity = function of `n` (how runtime increases as `n` increases)

> Think of it as: *“If I double the input, how much longer will it take?”*

---

# 🔹 Big O Notation

Most commonly, we describe complexity using **Big O notation**:

* `O(1)` → Constant time → doesn’t matter how big `n` is, runtime stays the same
* `O(log n)` → Logarithmic → grows slowly, very efficient (e.g., binary search)
* `O(n)` → Linear → grows directly with input size (e.g., traversing an array)
* `O(n log n)` → Linearithmic → typical for efficient sorting (merge sort, quicksort)
* `O(n^2)` → Quadratic → nested loops (like bubble sort)
* `O(2^n)` → Exponential → recursion without optimization (like naive Fibonacci)

---

# 🔹 How to Calculate Time Complexity

1. **Count basic operations**

   * Look at loops, recursion, and function calls
   * Focus on how many times a statement runs as `n` grows

2. **Nested Loops**

   ```python
   for i in range(n):
       for j in range(n):
           print(i, j)
   ```

   * Outer loop = n iterations
   * Inner loop = n iterations
   * Total = n × n = **O(n²)**

3. **Sequential loops**

   ```python
   for i in range(n):
       print(i)
   for j in range(n):
       print(j)
   ```

   * First loop = n
   * Second loop = n
   * Total = n + n = 2n → drop constants → **O(n)**

4. **Conditional statements**

   ```python
   if n > 10:
       print("hi")
   ```

   * Single operation → **O(1)**

5. **Recursion**

   ```python
   def fib(n):
       if n <= 1:
           return n
       return fib(n-1) + fib(n-2)
   ```

   * Each call spawns 2 calls → exponential growth → **O(2^n)**

---

# 🔹 Tips for Calculating

1. **Drop constants**

   * `O(2n)` → `O(n)`
   * `O(3n^2 + 5n)` → `O(n²)`

2. **Keep the fastest-growing term**

   * Nested loops dominate linear loops
   * Exponential dominates polynomial

3. **Focus on worst-case** (Big O)

   * Sometimes we also care about `Ω` (best-case) or `Θ` (average-case)

---

# 🔹 Examples in DSA Context

| Problem                       | Complexity |
| ----------------------------- | ---------- |
| Find max in array             | O(n)       |
| Check if array is sorted      | O(n)       |
| Binary search in sorted array | O(log n)   |
| Bubble sort                   | O(n²)      |
| Merge sort                    | O(n log n) |
| Fibonacci (naive recursion)   | O(2^n)     |

---

# ⚡ Mental model

* 1 loop → linear
* 2 nested loops → quadratic
* Dividing search space → logarithmic
* Exponentially branching recursion → exponential

---

Let’s go deep and really build a **complete, detailed understanding of time complexity**, including why we drop constants, logarithms, `n log n`, and a full ranking of complexities from fastest to slowest. 

---

# ⏱ Time Complexity – Detailed Guide

Time complexity is a measure of **how the runtime of an algorithm grows as the input size (`n`) grows**.

We analyze it to:

1. Compare algorithms
2. Predict performance on large inputs
3. Avoid solutions that “work for small inputs but fail for large inputs”

---

## 1️⃣ Big O Notation

**Big O notation** expresses **the upper bound of runtime growth**. It tells us **how the algorithm behaves in the worst-case scenario** as input size increases.

* Focus on **growth rate**, not exact runtime
* Ignore machine speed, exact number of operations, or constants

---

## 2️⃣ Why We Drop Constants

Suppose you have an algorithm that takes:

```
T(n) = 3n + 5
```

* For `n = 1`, T(n) = 8 → exact time matters
* For `n = 1,000,000`, T(n) = 3,000,005 → the +5 is negligible
* Constants do **not affect growth** as n → ∞

✅ So we write:

```
T(n) = 3n + 5 → O(n)
```

> **Rule:** Big O only cares about the **dominant term** as input grows.

---

## 3️⃣ Common Time Complexities

Here’s a **full list** from fastest (best) to slowest (worst) with explanations:

| Complexity     | Name         | When it occurs                                              | Example                                          |
| -------------- | ------------ | ----------------------------------------------------------- | ------------------------------------------------ |
| **O(1)**       | Constant     | No loops, single operation                                  | Accessing an array element `arr[5]`              |
| **O(log n)**   | Logarithmic  | Divide-and-conquer algorithms                               | Binary search, searching in a balanced BST       |
| **O(n)**       | Linear       | Single loop over n elements                                 | Finding max/min in an array                      |
| **O(n log n)** | Linearithmic | Efficient sorting, combining divide & conquer + linear work | Merge Sort, Heap Sort, Quick Sort (average case) |
| **O(n²)**      | Quadratic    | Nested loops                                                | Bubble Sort, Insertion Sort, Selection Sort      |
| **O(n³)**      | Cubic        | 3 nested loops                                              | Floyd-Warshall algorithm                         |
| **O(2^n)**     | Exponential  | Recursion that doubles each call                            | Naive Fibonacci, subset generation               |
| **O(n!)**      | Factorial    | Generating all permutations                                 | Traveling Salesman Brute-force                   |

---

## 4️⃣ Why `log n` appears

* When you **halve the input at each step**, the number of steps is `log₂ n`
* Examples:

```python
# Binary search halves array each time
low = 0
high = n-1
while low <= high:
    mid = (low+high)//2
```

* Number of iterations ≈ `log₂ n`
* Much faster than `O(n)` for large `n`

---

## 5️⃣ Why `n log n` appears

* Many **divide-and-conquer algorithms** do `O(log n)` splits, but at **each level do O(n) work**
* Example: Merge Sort

```
n elements → split in half (log n levels)
Merge at each level → n comparisons
Total = n * log n
```

* Faster than `O(n²)` but slower than `O(n)`

---

## 6️⃣ Visual growth comparison

Imagine n = 10⁶:

| Complexity | Approx steps      |
| ---------- | ----------------- |
| O(1)       | 1                 |
| O(log n)   | 20                |
| O(n)       | 1,000,000         |
| O(n log n) | 20,000,000        |
| O(n²)      | 1,000,000,000,000 |
| O(2^n)     | HUGE (impossible) |
| O(n!)      | Unthinkable       |

> Notice how constants are irrelevant — `20,000,000` is roughly 2n log n, constants like `+5` are tiny.

---

## 7️⃣ How to calculate Time Complexity – Step-by-step

1. **Count loops and nested loops**

   * Outer loop = n → inner loop = n → O(n²)
   * Multiple independent loops → add → O(n + n) → O(n)

2. **Look for recursion**

   * Each recursive call may generate multiple calls → exponential
   * Recursion halving input → logarithmic

3. **Ignore constants and lower-order terms**

   * T(n) = 3n² + 2n + 7 → O(n²)

4. **Watch for combined operations**

   * Linear + linearithmic → O(n + n log n) → O(n log n)

---

## 8️⃣ Quick Reference Order – Fastest to Slowest

```
O(1) < O(log n) < O(n) < O(n log n) < O(n^2) < O(n^3) < O(2^n) < O(n!)
```

---

## 9️⃣ Key Takeaways

* Time complexity helps **predict scalability**
* Always focus on the **dominant term**
* Logarithms → halving, binary search
* Linearithmic → divide & conquer + linear work
* Exponential / factorial → try to **avoid** for large inputs

---

