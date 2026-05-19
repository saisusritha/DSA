
---

# 🗂 Space Complexity – Complete Guide

Space complexity measures **the total amount of memory an algorithm uses** relative to its input size `n`. It helps us understand **how much memory our code will need**, which is just as important as runtime, especially for large inputs.

---

## 1️⃣ Components of Space Complexity

When analyzing an algorithm’s space usage, consider **three main components**:

1. **Input Space**

   * Memory needed to store the input
   * Example: An array of `n` integers → O(n) space

2. **Auxiliary/Extra Space**

   * Temporary variables, arrays, hash maps, queues, stacks, etc.
   * Example: Merge Sort uses a temporary array for merging → O(n) extra space

3. **Function Call Stack**

   * Each recursive call consumes memory on the stack
   * Example: Recursive Fibonacci (naive) → O(n) stack memory

> Total Space Complexity = Input Space + Auxiliary Space + Recursion Stack

---

## 2️⃣ Why Space Complexity Matters

* High memory usage can **crash programs** or slow down execution
* Important for **competitive programming, embedded systems, and big data**
* Helps **choose optimal algorithms** not just for speed but also memory efficiency

---

## 3️⃣ Common Space Complexities

| Complexity     | Name         | When it occurs                                                   | Example                                            |
| -------------- | ------------ | ---------------------------------------------------------------- | -------------------------------------------------- |
| **O(1)**       | Constant     | No extra memory used except a few variables                      | Swapping two numbers, iterative factorial          |
| **O(log n)**   | Logarithmic  | Recursion where input halves each step                           | Recursive binary search                            |
| **O(n)**       | Linear       | Storing arrays, linked lists, recursion stack                    | DFS traversal using recursion, storing input array |
| **O(n log n)** | Linearithmic | Divide & conquer algorithms with linear extra work at each level | Merge Sort (temporary arrays)                      |
| **O(n²)**      | Quadratic    | 2D structures or nested loops creating arrays                    | Storing adjacency matrix for graphs                |
| **O(2^n)**     | Exponential  | Recursion generating all subsets or combinations                 | Naive recursive Fibonacci, subset generation       |
| **O(n!)**      | Factorial    | Storing all permutations                                         | Brute-force TSP solution                           |

---

## 4️⃣ How to Calculate Space Complexity

### 4.1 Count Variables

```python
a = 5        # O(1)
b = 10       # O(1)
arr = [1,2,3]  # O(n)
```

* Individual variables → O(1)
* Arrays/lists → O(n)

---

### 4.2 Consider Loops

```python
for i in range(n):
    print(i)
```

* Looping **does not increase space** unless new structures are created inside
* This example → O(1) space

---

### 4.3 Consider Recursion

```python
def factorial(n):
    if n == 0:
        return 1
    return n * factorial(n-1)
```

* Recursive calls create a stack frame for each call → O(n) space
* Iterative version → O(1) space

---

### 4.4 Consider Extra Structures

```python
temp = []
for i in range(n):
    temp.append(i)  # temp grows with n → O(n)
```

* Any new arrays, hash maps, or queues count toward space complexity

---

## 5️⃣ Examples of Space Complexity

| Algorithm                                   | Time Complexity | Space Complexity                         | Notes                                           |
| ------------------------------------------- | --------------- | ---------------------------------------- | ----------------------------------------------- |
| Bubble Sort                                 | O(n²)           | O(1)                                     | In-place sorting, no extra memory needed        |
| Merge Sort                                  | O(n log n)      | O(n)                                     | Uses temporary arrays for merging at each level |
| Binary Search                               | O(log n)        | O(1) iterative / O(log n) recursive      | Recursive stack adds memory                     |
| Fibonacci (Naive Recursion)                 | O(2^n)          | O(n)                                     | Stack space dominates, many duplicate calls     |
| Fibonacci (Dynamic Programming / Iterative) | O(n)            | O(n) memoization array or O(1) optimized | Constant memory if we store only last 2 results |

---

## 6️⃣ Recursive vs Iterative Memory Usage

| Approach  | Memory Usage | Example                                                  |
| --------- | ------------ | -------------------------------------------------------- |
| Iterative | Usually O(1) | Iterative factorial, iterative Fibonacci                 |
| Recursive | O(depth)     | Recursive factorial → O(n), Binary tree traversal → O(h) |

> Recursion can be elegant but memory-expensive for **deep recursion**

---

## 7️⃣ Space Optimization Tips

1. **Use in-place algorithms**

   * Example: Bubble Sort or Heap Sort doesn’t create extra arrays

2. **Reuse memory whenever possible**

   * Avoid creating temporary arrays repeatedly

3. **Convert recursion to iteration**

   * Saves stack memory

4. **Avoid unnecessary data structures**

   * Example: Use a single array instead of two separate arrays if possible

5. **Use memoization wisely**

   * Helps reduce time complexity but increases memory usage

---

## 8️⃣ Quick Reference: Space Complexity Rankings

```text
O(1) < O(log n) < O(n) < O(n log n) < O(n²) < O(2^n) < O(n!)
```

* Less memory → faster, safe for large inputs
* More memory → slower, risky for large inputs

---

## 9️⃣ Key Takeaways

* Space complexity tells **how much memory your code consumes**
* Always consider **variables, recursion stack, and auxiliary structures**
* Optimizing space is as important as optimizing time
* Recursive algorithms often increase memory usage due to stack frames

---


