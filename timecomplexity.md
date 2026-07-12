# Big O Notation

## What is Big O?

### Definition

Big O notation describes how the number of operations performed by an algorithm grows as the input size (`n`) increases.

### Simple Definition

Big O measures how efficiently an algorithm performs as the input size gets larger.

## Why Do We Use Big O?

Big O helps us:

* Compare the efficiency of different algorithms.
* Predict how an algorithm will perform for large inputs.
* Measure the growth rate of an algorithm rather than its actual execution time.
* Evaluate algorithms independently of hardware, programming language, or compiler.

## What is `n`?

`n` represents the size of the input.

Example:

```python
arr = [10, 20, 30, 40, 50]
```

Here:

```
n = 5
```

If the array contains 100 elements:

```
n = 100
```

## Example

Algorithm A

```python
for i in range(n):
    print(i)
```

Time Complexity: **O(n)**

Algorithm B

```python
for i in range(n):
    for j in range(n):
        print(i, j)
```

Time Complexity: **O(n²)**

Although both algorithms may seem fast for small inputs, Algorithm A scales much better as the input size increases.

## Order of Big O

| Complexity   | Name         | Description    |
| ------------ | ------------ | -------------- |
| `O(1)`       | Constant     | Best           |
| `O(log n)`   | Logarithmic  | Very Fast      |
| `O(n)`       | Linear       | Good           |
| `O(n log n)` | Linearithmic | Efficient      |
| `O(n²)`      | Quadratic    | Slow           |
| `O(n³)`      | Cubic        | Very Slow      |
| `O(2ⁿ)`      | Exponential  | Extremely Slow |
| `O(n!)`      | Factorial    | Worst          |

## Common Big O Patterns

### O(1) — Constant Time

The amount of work remains the same regardless of the input size.

Example:

```python
arr[3]
```

```python
x = arr[0]
```

Whether the array contains 10 elements or 1,000,000 elements, accessing an element requires the same amount of work.

### O(log n) — Logarithmic Time

The problem size is reduced during each iteration, usually by half.

Example:

```python
while n > 1:
    n = n // 2
```

Common example:

* Binary Search

Example reduction:

```
32
16
8
4
2
1
```

### O(n) — Linear Time

The algorithm processes every element once.

Example:

```python
for i in range(n):
    print(i)
```

If the input size doubles, the amount of work also doubles.

### O(n log n) — Linearithmic Time

A linear amount of work combined with logarithmic work.

Common examples:

* Merge Sort
* Heap Sort
* Quick Sort (Average Case)

### O(n²) — Quadratic Time

Two nested loops.

Example:

```python
for i in range(n):
    for j in range(n):
        print(i, j)
```

Total work:

```
n × n = n²
```

### O(n³) — Cubic Time

Three nested loops.

Example:

```python
for i in range(n):
    for j in range(n):
        for k in range(n):
            print(i, j, k)
```

Total work:

```
n × n × n = n³
```

### O(2ⁿ) — Exponential Time

Each step branches into two possible choices.

Common example:

* Naive Recursive Fibonacci

### O(n!) — Factorial Time

The algorithm tries every possible arrangement.

Common example:

* Brute-force permutation algorithms

## Rules for Calculating Big O

### Rule 1: One Loop

```python
for i in range(n):
    pass
```

Time Complexity:

```
O(n)
```

### Rule 2: Consecutive Loops

```python
for i in range(n):
    pass

for j in range(n):
    pass
```

Calculation:

```
O(n) + O(n)
= O(2n)
= O(n)
```

Add the complexities, then simplify.

### Rule 3: Nested Loops

```python
for i in range(n):
    for j in range(n):
        pass
```

Calculation:

```
n × n
= O(n²)
```

Multiply the complexities.

### Rule 4: Halving Every Iteration

```python
while n > 1:
    n = n // 2
```

Time Complexity:

```
O(log n)
```

### Rule 5: Ignore Constants and Lower-Order Terms

Examples:

```
O(5n) = O(n)

O(100n + 50) = O(n)

O(n² + n) = O(n²)

O(n + log n) = O(n)
```

## Time Complexity vs Space Complexity

| Time Complexity                              | Space Complexity                               |
| -------------------------------------------- | ---------------------------------------------- |
| Measures the number of operations performed  | Measures the extra memory used                 |
| Focuses on execution speed                   | Focuses on memory usage                        |
| Usually more important in algorithm analysis | Considered after time complexity in most cases |

## Key Points

* Big O does not measure actual execution time.
* It measures how the amount of work grows as the input size increases.
* Ignore constants and lower-order terms.
* Keep only the dominant term.
* A smaller Big O generally indicates better scalability.

## Summary

| Pattern                 | Time Complexity |
| ----------------------- | --------------- |
| Access an array element | `O(1)`          |
| One loop                | `O(n)`          |
| Two consecutive loops   | `O(n)`          |
| Two nested loops        | `O(n²)`         |
| Three nested loops      | `O(n³)`         |
| Halving each iteration  | `O(log n)`      |
| One loop + halving loop | `O(n)`          |
| Binary Search           | `O(log n)`      |
| Linear Search           | `O(n)`          |
| Merge Sort              | `O(n log n)`    |
| Heap Sort               | `O(n log n)`    |
| Quick Sort (Average)    | `O(n log n)`    |
